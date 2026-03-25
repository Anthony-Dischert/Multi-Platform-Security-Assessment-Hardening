# Linux Security Assessment and Hardening

## Overview

This phase documents the baseline collection, hardening actions, and validation results for a Linux Mint workstation.

The goal of this work was to apply practical security improvements appropriate for a daily-use personal system while maintaining normal usability. The focus was on improving host firewall posture, hardening SSH, adding brute-force protections, improving audit visibility, and documenting the changes with supporting evidence.

## System Context

- System type: Personal workstation
- Operating system: Linux Mint
- Use case: Daily-use desktop system
- Scope: Practical workstation hardening
- Approach: Baseline -> hardening -> validation

Because this is a personal machine, security decisions were made with usability in mind rather than pursuing maximum lockdown.

## Project Structure

- `baseline/` — pre-hardening system state and evidence
- `hardening/` — configuration changes and control summaries
- `validation/` — post-hardening verification evidence

## Baseline Collection

The baseline phase captured the starting state of the system before changes were applied. This included:

- System information
- CPU and memory information
- Disk usage
- Logged-in users
- Network interfaces
- Open ports
- Firewall status
- Running services
- Service startup status
- Package count
- Package update status

This created a documented "before" snapshot that could be compared against the hardened state.

## Hardening Actions Applied

The following hardening actions were implemented:

### Firewall
- Enabled and configured UFW
- Applied a default deny inbound policy
- Allowed SSH explicitly
- Recorded resulting firewall status and rules

### SSH Hardening
- Disabled root login
- Applied authentication attempt limits
- Applied idle session timeout settings
- Saved resulting SSH configuration evidence

### Fail2ban
- Installed and configured Fail2ban
- Enabled SSH brute-force protection
- Verified jail status after configuration

### Auditing and Visibility
- Configured audit-related validation for privileged command activity
- Verified sudo-related audit evidence

### System Review and Operational Decisions
- Reviewed running services and exposed ports
- Reviewed package/update state
- Evaluated AIDE, but chose not to deploy it because it was not practical for a dynamic daily-use desktop environment

## Validation

Validation evidence was collected after hardening and stored in the `validation/` directory. This includes confirmation of:

- Firewall status after changes
- Firewall rules after changes
- Final open ports
- Fail2ban jail status
- Fail2ban ban testing
- Fail2ban logs
- SSH protection status
- Sudo audit-related validation

## Security Decisions and Tradeoffs

This project intentionally prioritized realistic hardening over unnecessary disruption.

Examples of decisions made during this phase:

- AIDE was evaluated but not deployed because desktop systems generate frequent file changes that would make integrity monitoring noisy and less practical
- Services required for normal workstation use were not removed simply for appearance
- Hardening focused on controls that clearly improved security posture while still fitting a personal daily-use system

## Outcome

This Linux phase resulted in a documented and validated workstation hardening baseline.

The system now has:

- Improved firewall posture
- Hardened SSH configuration
- Brute-force protection through Fail2ban
- Better audit visibility
- Documented before-and-after evidence
- Version-controlled hardening artifacts

## Status

- Linux phase: Complete
