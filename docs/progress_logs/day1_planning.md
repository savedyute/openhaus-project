# Day 1 – Planning & Project Setup
**Date:** September 23, 2025

## Goals
- Define project scope and objectives
- Plan network architecture
- List hardware and VMs needed
- Set up repository structure

## Tasks Completed
- Defined OpenHaus scope: secure Wi-Fi and vendor marketplace for campuses
- Planned network architecture: ISP → pfSense VM → Switch → TP-Link AP → Users, with Ubuntu VM and MacBook on switch
- Created GitHub repo (`openHaus-project`) with /docs, /configs, /captive_portal, /website, /mobile_app, /scripts
- Drafted initial README and /docs files (project_overview.md, network_architecture.md)
- Created network architecture diagram in Lucidchart (/docs/images/network_architecture.png)
- Pushed initial project folder to GitHub[](https://github.com/savedyute/openhaus-project)

## Issues / Challenges
- Encountered Git merge conflict with .DS_Store (macOS metadata file) due to divergent branch histories
- Resolved conflict by removing .DS_Store and committing the merge
- Faced editor issue with vi during commit, switched to command-line message option (-m) to proceed

## Next Steps
- Install and configure pfSense VM (WAN/LAN setup)
- Set up Ubuntu VM with static IP
- Connect TP-Link AP to switch
- Document hardware setup with photos in /docs/setup_notes.md

## Reflections
- Successfully set up the repo structure and drafted key documentation files
- Lucidchart was effective for creating the network diagram, aligning with OpenHaus branding
- Git challenges were resolved with guidance, improving my version control skills
- Excited to start hardware setup and pfSense configuration tomorrow!