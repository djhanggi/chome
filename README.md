# This is my home server setup

## Formatting

To format, use `prettier --write **/*.yaml` with the existing .prettierrc.yaml. 

Keys should be sorted in the order specified in the .sort-order*.yaml files.

## TODOs

### Next

- Docker Networking

  - Want to minimize use of host and define manual Docker networks to isolate
    services
  - Add a container to several networks if communication is necessary between
    them
  - Containers can reference each other via service name if on same network
  - Link PiHole DNS as main DNS
  - Specify hosts for PiHole DNS as source of truth where container/hostnames
    live (or this will be moved to pFsense)
  - Version control hosts file as .conf
- Migrate Cornell Calendar

- Migrate Cornell Calendar

- Docker / Pi / NAS Permissions (UID/GID)
  - read-only usually
  - Disable modification of existing files:
- Invalid file name characters (radio lab, , French class)
- Close router to public internet

### Networking / Admin

- PiHole DNS-over-HTTPS
- Manage networking/configuration/constants/secrets in separate repository
- fail2ban

### Storage

- Serve NAS via Synology or Syncthing to devices
- Clean up space regularly
- Auto-canonicalize photos
- Serve photos/media via Plex and Photos equivalent

### Home Assistant

- Notify on shutdown + startup
- Automate phone alarm and use as sunset time
- Move secrets to each individual package
- Air Conditioning
  - cycle_ac
    - If AC is on while automation.cycle_ac is turned on, start timer
    - Snooze automation.cycle_ac for an hour at start of sleep
  - Use virtual temperature to offset to mimic cycling
  - Set mode
  - Use derivative to figure out if AC is actually running + automatically
    correct
- Use YAML for dashboards

### Miscellaneous

- Standardize ordering of keys via script (global, then via nested YAML/yq path)
- Set up / back up status page with reverse proxy
- Set up homepage
- Move WiFi names to secrets
- Document setup for custom components and UI-managed items
- Use Proton Mail or self-hosted mail/calendar
- Create second PiHole instance
  - primary default forwards to secondary, falls back to open DNS
  - secondary blocks optional websites (like social media) and can be turned off
- [Matrix](https://github.com/spantaleev/matrix-docker-ansible-deploy/blob/master/docs/README.md)
  - Delete social media
  - Regularly purge chat applications
- Migrate Cornell Mail

# YAML Sorting

Getting all keys:
`yq '.. | select((tag == "!!map" or tag == "!!seq") | not) | path | .[]' | sort | uniq`

Replacing keys: `sed 's/key/slug/' | yq 'sort_keys(..)' | s/slug/key/'`
