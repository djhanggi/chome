# This is my home server setup

## Formatting

To format, use `prettier --write **/*.yaml` with the existing .prettierrc.yaml.

## TODOs

### Networking / Admin

- Create .txt of hosts/IP addresses for records and use in pihole & elsewhere
- Set up Docker networking and isolate services
- Manage networking/configuration/constants/secrets in separate repository
- PiHole DNS-over-HTTPS
- Permissions for file systems / Docker

### Storage

- Create NAS + UPS setup
  - Backup phones/laptops/Pi to NAS
  - bespin storage on NAS
  - regularly rsync this to the SSD stored in safe
  - regularly backup/encrypt to 2292 + Google Drive + connected SSD
  - regularly restic/backup to always-connected SSD
- Serve NAS via Synology or Syncthing to devices
- Serve photos/media via Plex and Photos equivalent
- Set maximum log size for nginx/pihole/home-assistant
  - Version-control .confs
- Migrate Google Drive

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

### Miscellaneous

- Set up Portainer and monitoring/status
- Move WiFi names to secrets
- Standardize ordering of keys
- Document setup for custom components and UI-managed items
- Migrate Cornell Drive/Mail/Calendar
- Use Proton Mail or self-hosted mail/calendar
- Create second PiHole instance
  - primary default forwards to secondary, falls back to open DNS
  - secondary blocks optional websites (like social media) and can be turned off
- Clean up space regularly
- [Matrix](https://github.com/spantaleev/matrix-docker-ansible-deploy/blob/master/docs/README.md)
  - Delete social media
  - Regularly purge chat applications
