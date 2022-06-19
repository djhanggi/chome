# This is my home server setup

## Formatting

To format, use `prettier --write **/*.yaml` with the existing .prettierrc.yaml.

## TODOs

- Standardize ordering of keys
- Create correction script for fan.dyson_heater_fan
- Use YAML for dashboards
- Automate phone alarm and use as sunset time
- Create .txt of hosts/IP addresses for records and use in pihole & elsewhere
- Create second PiHole instance
  - primary default forwards to secondary, falls back to open DNS
  - secondary blocks optional websites (like social media) and can be turned off
- Document setup for custom components and UI-managed items
- Move secrets to each individual package
- Manage networking/configuration/constants/secrets in separate repository
- Move WiFi names to secrets
