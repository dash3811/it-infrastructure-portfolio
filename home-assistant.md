# Home Assistant Automation

## Overview

Home Assistant is used as the central automation platform for smart devices, lighting, security alerts, presence detection, media routines, and notification workflows.

## Environment

- 44 connected smart devices
- YAML automations and scripts
- Lighting automations
- Presence and motion detection
- Camera/person detection alerts
- Soundbar/media routines
- Mobile notifications

## Skills Demonstrated

- YAML configuration
- Event-based automation
- Device integration
- Notification workflows
- Troubleshooting entities, triggers, conditions, and actions
- Smart-home security and monitoring logic

## Example Automation: Sanitized Motion Lighting

```yaml
alias: Example Motion Lighting
description: Sanitized sample automation
trigger:
  - platform: state
    entity_id: binary_sensor.example_motion
    to: "on"
condition:
  - condition: time
    after: "07:00:00"
    before: "23:00:00"
action:
  - service: light.turn_on
    target:
      entity_id: light.example_room
    data:
      brightness_pct: 80
mode: restart
```

## Example Automation: Sanitized Notification

```yaml
alias: Example Door Notification
trigger:
  - platform: state
    entity_id: binary_sensor.example_door
    to: "on"
action:
  - service: notify.mobile_app_example_phone
    data:
      title: "Door Opened"
      message: "The example door was opened."
mode: single
```

## Documentation To Add

- 2 or 3 sanitized automations
- Short explanation of the problem each automation solves
- Screenshots only if they contain no private information
- Notes on troubleshooting automations
