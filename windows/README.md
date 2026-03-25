# Windows Security Assessment and Hardening

## Overview

This phase documents the baseline collection, hardening actions, and validation results for a personal Windows workstation.

The goal of this work was to apply practical security improvements that make sense for a daily-use home system without introducing unnecessary usability issues. The focus was on reducing exposed services, improving visibility through logging, strengthening built-in protections, and documenting each change with validation evidence.

## System Context

- System type: Personal workstation
- Use case: Daily-use home computer
- Scope: Practical workstation hardening
- Approach: Baseline -> hardening -> validation

Because this is a personal machine, some aggressive enterprise-style controls were intentionally not applied if they would make normal use unnecessarily disruptive.

## Project Structure

- `baseline/` — pre-hardening system state and evidence
- `hardening/` — transcript of hardening actions performed (Ommitted *See Privacy Notes)
- `validation/` — post-hardening verification evidence

## Baseline Collection

The baseline phase captured the system state before changes were made. This included:

- System and OS information
- Microsoft Defender status and preferences
- Firewall profile configuration
- Local users and administrators
- Running services and startup items
- Open TCP and UDP endpoints
- Installed updates
- BitLocker status
- Audit policy
- Local security policy
- Remote Desktop status
- SMBv1 status
- UAC settings
- Available event logs

This baseline provides a documented "before" snapshot for comparison and validation.

## Hardening Actions Applied

The following hardening actions were implemented:

### Firewall
- Enabled firewall logging for allowed and blocked traffic
- Increased firewall log size
- Captured post-change firewall profile validation

### Microsoft Defender
- Confirmed real-time protection was enabled
- Enabled behavior monitoring
- Enabled script scanning
- Enabled network protection
- Enabled cloud-delivered protection at a higher reporting level
- Enabled PUA protection
- Captured post-change Defender settings

### Auditing and Logging
- Enabled auditing for:
  - Logon events
  - Credential validation
  - Sensitive privilege use
  - Audit policy change
  - Process creation
- Exported post-hardening audit policy and local security policy

### Remote Access Reduction
- Disabled Remote Desktop
- Verified RDP disablement
- Evaluated firewall rules related to RDP exposure

### Legacy Protocol and Remote Service Reduction
- Disabled SMBv1
- Disabled Remote Registry
- Disabled WinRM after confirming it was not actively configured for use

### Network Exposure Reduction
- Disabled Network Discovery firewall rules
- Disabled File and Printer Sharing firewall rules

### Built-in Account Hardening
- Disabled the built-in Administrator account
- Disabled the Guest account

### Account Lockout Protection
- Applied account lockout protections
- Retained user-friendly password length settings appropriate for a personal workstation

## Validation

Validation evidence was collected after hardening and stored in the `validation/` directory. This includes confirmation of:

- Firewall profile and logging state
- Defender configuration
- Audit policy changes
- Remote Desktop disablement
- SMBv1 disablement
- Remote Registry disablement
- WinRM disablement
- Network Discovery disablement
- File and Printer Sharing disablement
- Administrator and Guest account disablement
- Account lockout policy
- Windows Update service status
- Recent installed updates
- Post-hardening local security policy

## Security Decisions and Tradeoffs

This project intentionally prioritized realistic hardening over maximum possible lockdown.

Examples of controls that were evaluated but intentionally limited or skipped:

- Strict password length requirements were not enforced because this is a personal daily-use system
- More aggressive enterprise-focused controls were not applied because they were outside the scope of a practical home workstation baseline
- The goal was to improve security posture without creating unnecessary friction in normal use

## Outcome

This Windows phase resulted in a documented, validated, and portfolio-ready workstation hardening baseline.

The system now has:

- Improved logging and audit visibility
- Reduced remote access exposure
- Reduced legacy protocol exposure
- Stronger built-in endpoint protection settings
- Hardened built-in account posture
- Version-controlled baseline and validation evidence

## Status

Windows phase complete.
