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

## Kitchen Lights Automation: Sanitized Motion Lighting

Turns on the kitchen lights when someone enters and waits 2 mins for no presence before dimming them to off. 

```yaml
alias: Kitchen Lights Motion Automation
description: >
  Turn on kitchen lights with motion (to white) and turn off after 2 min of no
  motion—blocked while Home Sexy mode is active.
triggers:
  - entity_id: binary_sensor.kitchen_radar_moving_target
    from: "off"
    to: "on"
    trigger: state
conditions:
  - condition: state
    entity_id: input_boolean.home_sexy_mode
    state: "off"
actions:
  - target:
      entity_id: light.kitchen
    data:
      brightness_pct: 100
      color_name: white
    action: light.turn_on
  - wait_for_trigger:
      - entity_id: binary_sensor.kitchen_radar_moving_target
        from: "on"
        to: "off"
        for:
          minutes: 2
        trigger: state
  - target:
      entity_id: light.kitchen
    data:
      transition: 60
    action: light.turn_off
mode: restart
```

## Door Open Notification: Sanitized Notification

Notifies me if my front or rear door is open for security. 

```yaml
alias: Notify Door Open with Delay
description: >
  Notify immediately for most doors and notify after 2 minutes for the
  refrigerator. Repeat reminders every 15 seconds until closed.
triggers:
  - entity_id:
      - binary_sensor.front_door_contact
    from:
      - "off"
    to:
      - "on"
    trigger: state
actions:
  - choose:
      - conditions:
          - condition: template
            value_template: |
              {{ trigger.entity_id != 'binary_sensor.fridge_door_contact' }}
        sequence:
          - repeat:
              for_each:
                - notify.alexa_media_ecobee_thermostat
                - notify.google_assistant_sdk
              sequence:
                - data:
                    message: "{{ trigger.to_state.attributes.friendly_name }} is open!"
                  action: "{{ repeat.item }}"
  - delay: "00:02:00"
  - repeat:
      while:
        - condition: template
          value_template: "{{ is_state(trigger.entity_id, 'on') }}"
      sequence:
        - repeat:
            for_each:
              - notify.alexa_media_ecobee_thermostat
              - notify.google_assistant_sdk
            sequence:
              - data:
                  message: >-
                    Reminder: {{ trigger.to_state.attributes.friendly_name }} is
                    still open!
                action: "{{ repeat.item }}"
        - delay: "00:00:15"
mode: restart
```


