---
title: "Linux systemd timers"
aliases:
  - "systemd timers"
type: note
classification: QA76
classification_label: Computer software
classification_source: lcc
primary_moc: Linux
related_mocs: []
tags:
  - linux
  - systemd
  - automation
created: "2026-06-19T00:00:00"
updated: "2026-06-19T00:00:00"
---

# Linux systemd timers

## Summary

Systemd timers schedule services to run at a particular time or after a defined interval. They provide a Linux-native alternative to cron when a task benefits from service dependencies, centralized logs, or missed-run handling.

## Details

A scheduled task normally uses two units with the same base name:

- A `.service` unit defines the command to run.
- A `.timer` unit defines when systemd activates that service.

Useful timer settings include `OnCalendar` for calendar-based schedules, `OnBootSec` or `OnUnitActiveSec` for relative intervals, and `Persistent=true` when a missed calendar run should execute after the machine starts again.

Common inspection commands are:

```bash
systemctl list-timers
systemctl status example.timer
journalctl -u example.service
```

## Related

- [[linux|Linux]]
