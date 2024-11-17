---
name: Performance issue
about: Help me optimize
title: ''
labels: ''
assignees: ''

---

name: ⚡ Performance Issue
description: Report a performance problem
title: "[PERFORMANCE] "
labels: ["performance"]
body:
  - type: markdown
    attributes:
      value: |
        Thanks for reporting a performance issue!
  - type: textarea
    id: reproduction
    attributes:
      label: Steps to reproduce
      description: How can we see this performance issue?
      placeholder: |
        1. Open the game
        2. Buy X upgrades
        3. Notice lag when...
    validations:
      required: true
  - type: input
    id: device
    attributes:
      label: Device
      description: What device/platform are you using?
      placeholder: "Desktop Chrome, iPhone Safari, etc."
    validations:
      required: true
  - type: textarea
    id: performance-data
    attributes:
      label: Performance Data
      description: If possible, include FPS, memory usage, or other relevant metrics
