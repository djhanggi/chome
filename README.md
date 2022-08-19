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

- Permissions for file systems / Docker
- uid/gid
- NAS
  - Backup phones to NAS
  - Encrypt/backup NAS to 2292 and connected SSD
  - Encrypt/mirror NAS to SSD
- Set up Docker networking and isolate services
- Version-control .confs

### Networking / Admin

- PiHole DNS-over-HTTPS
- Create .txt of hosts/IP addresses for records and use in pihole & elsewhere
- Manage networking/configuration/constants/secrets in separate repository

### Storage

- Google Drive clean-up / archiving / migration
- Serve NAS via Synology or Syncthing to devices
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

- Set up Portainer and monitoring/status
- Set up monitoring/status webpage
- Move WiFi names to secrets
- Standardize ordering of keys via script
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
