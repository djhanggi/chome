# This is my home server setup

## Setup

This server is mostly managed through docker-compose, and thus as simple as
running the compose files. Manual setup includes:

- Install Docker
- Install
  [docker-compose](https://docs.linuxserver.io/images/docker-docker-compose)
- Home Assistant
  - Android TV
  - Broadlink
  - ConBee
  - Google Calendar
  - HACS
    - Adaptive Lighting
    - Wyze
  - PiHole
  - Plex
  - Spotify
  - Synology
  - Tuya

## Formatting

To format, use `prettier --write **/*.yaml` with the existing .prettierrc.yaml.

Keys should be sorted in the order specified in the .sort-order\*.yaml files.

## Bitwarden Linting

- Serial numbers should be placed in the Serial Numbers secure note
- Put a member number in the respective Login entry, unless there is none; then
  put in the Rewards Card Numbers secure note
- Put recovery codes in the Authenticator Backup Codes secure note and the
  corresponding login entry
- Don't duplicate attachments or entries in the identity entry
- Sort custom fields alphabetically

## TODOs

### Next

- zstyle for zsh + ohmyzsh
- /mnt/{chome,docker} vs. on SSD
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
  - read-only usually
  - Disable modification of existing files

### Networking / Admin

- PiHole DNS-over-HTTPS
- Manage networking/configuration/constants/secrets in separate repository
- fail2ban
- Restrict most access to behind VPN unless specifically required
  - HA behind VPN
- Firefox Relay, Privacy Card, & VPN

### Storage

- Clean up space regularly
- Serve NAS via Synology or Syncthing to devices
- Serve photos/media via Plex and Photos equivalent
- Auto-canonicalize photos
- Encrypt /documents + setup protection rules
- Set up file + photo serving and deprecate Google

### Home Assistant

- Automate phone alarm and use as sunset time

### Miscellaneous

- Canonicalizing photo script
- Diff tool
- Standardize ordering of keys via script (global, then via nested YAML/yq path)
- Set up / back up status page with reverse proxy
- Set up homepage
- Move WiFi names to secrets
- Create second PiHole instance
  - primary default forwards to secondary, falls back to open DNS
  - secondary blocks optional websites (like social media) and can be turned off
- [Matrix](https://github.com/spantaleev/matrix-docker-ansible-deploy/blob/master/docs/README.md)
  - Delete social media
  - Regularly purge chat applications
- Use Proton Mail or self-hosted mail/calendar
- Migrate Cornell Mail
- Research free + reputable news providers
- Research privacy-focused keyboard for Android + iOS

### Bitwarden

- Sort custom fields alphabetically except for predefined order
- Use hidden fields

### YAML Sorting

Getting all keys:
`yq '.. | select((tag == "!!map" or tag == "!!seq") | not) | path | .[]' | sort
| uniq`

Replacing keys: `sed 's/key/slug/' | yq 'sort_keys(..)' | s/slug/key/'`
