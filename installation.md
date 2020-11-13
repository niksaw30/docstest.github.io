---
title: {{ main.frontmatter.title }}
subtitle: # Will be auto-populated
description: {{ main.frontmatter.description }}
date: # Will be auto-populated
---

\newpage

# Architecture
{{ architecture }}

# Technical Requirements

## Hardware

### CPU
{{ main.requirements.hardware.cpu }}

### RAM
{{ main.requirements.hardware.memory.main }}

### Storage

Services and Docker Containers require: {{ main.requirements.hardware.storage.docker_and_services }}

SWAP Memory: {{ main.requirements.hardware.memory.swap }}

{% if main.requirements.hardware.docs %}
| Number of docs (assuming docx format of 1mb each) | Hard Drive Space Required |
| ------------------------------------------------- | ------------------------- |
{% for row in main.requirements.hardware.docs -%} 
| {{ row.count }} | {{ row.storage }} |
{% endfor %}
{% endif %}

## Software

The following software is required across all installations methods, with version number in brackets. Further requirements specific to installation methods are listed later.

{% for platform in main.requirements.software.platforms -%}
* {{ platform }}
{% endfor %}

### Supported Browsers