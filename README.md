# This is my home server setup

## Formatting

To format, use `prettier --write **/*.yaml` with the existing .prettierrc.yaml.

The following order is used for docker-compose YAML:

- container_name
- image
- network_mode
- ports
- environment
- volumes
- devices
- options
- cap_add
- privileged
- security_opt
- sysctls
- logging
- restart

## TODOs

### Next

- /mnt/docker/ on bespin
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

- Docker / Pi / NAS Permissions (UID/GID)
- NAS
  - Encrypt/backup NAS to 2292 and connected SSD
  - Encrypt/mirror NAS to SSD
- Close router to public internet

### Networking / Admin

- PiHole DNS-over-HTTPS
- Manage networking/configuration/constants/secrets in separate repository
- fail2ban

### Storage

- Google Drive clean-up / archiving / migration
- Serve NAS via Synology or Syncthing to devices
- Clean up space regularly
- Auto-canonicalize photos
- Serve photos/media via Plex and Photos equivalent

### Home Assistant

- Automate phone alarm and use as sunset time
- Move secrets to each individual package
- Use YAML for dashboards
- Air Conditioning
  - cycle_ac
    - If AC is on while automation.cycle_ac is turned on, start timer
    - Snooze automation.cycle_ac for an hour at start of sleep
  - Use virtual temperature to offset to mimic cycling
  - Set mode
- Notify on shutdown
- Standardize ordering of keys in HASS

### Miscellaneous

- Standardize ordering of keys via script
- Set up / back up status page with reverse proxy
- Set up homepage
- Move WiFi names to secrets
- Document setup for custom components and UI-managed items
- Migrate Cornell Drive/Mail/Calendar
- Use Proton Mail or self-hosted mail/calendar
- Create second PiHole instance
  - primary default forwards to secondary, falls back to open DNS
  - secondary blocks optional websites (like social media) and can be turned off
- [Matrix](https://github.com/spantaleev/matrix-docker-ansible-deploy/blob/master/docs/README.md)
  - Delete social media
  - Regularly purge chat applications

# Getting YAML Keys

<!-- yq '.. | select((tag == "!!map" or tag == "!!seq") | not) | path | .[]' | sort | uniq -->

# Sorting

<!-- sed 's/key/slug/' | yq 'sort_keys(..)' | s/slug/key/' -->
