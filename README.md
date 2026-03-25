# Multi-Platform Security Assessment and Hardening

## Overview

This repository documents a multi-platform workstation security hardening project across Linux and Windows environments.

The purpose of the project is to assess baseline system security, apply practical hardening measures, validate the results, and document the process in a way that is useful for both learning and portfolio presentation.

The work focuses on realistic endpoint hardening for personal daily-use systems rather than enterprise compliance implementation.

## Project Goals

- Establish a documented security baseline before changes
- Apply practical hardening controls
- Validate that the controls were successfully implemented
- Maintain clear evidence artifacts for each phase
- Present the work in a structured, professional format

## Repository Structure

- `linux/`
  - `README.md`
  - `baseline/`
  - `hardening/` *(omitted from the public version; see Privacy Note)*
  - `validation/`
- `windows/`
  - `README.md`
  - `baseline/`
  - `hardening/`
  - `validation/`
- `README.md`

## Linux Phase

The Linux phase focused on workstation hardening for a Linux Mint system.

Implemented areas included:

- Baseline system collection and documentation
- UFW firewall configuration
- Fail2ban deployment and SSH brute-force protection
- SSH hardening
- Audit-related validation
- Running services and open-port review
- Package update and service-state review
- Security documentation and evidence capture

AIDE was evaluated during the Linux phase but was not deployed because it was not considered practical for a dynamic daily-use desktop environment. Audit-focused validation was used instead.

Linux phase status: Complete

See `linux/README.md` for details.

## Windows Phase

The Windows phase focused on practical hardening for a personal Windows workstation using built-in Windows security controls and PowerShell-based validation.

Implemented areas included:

- Baseline system and security state collection
- Windows Firewall logging configuration
- Microsoft Defender hardening
- Audit policy hardening
- Remote Desktop disablement
- SMBv1 disablement
- Remote Registry disablement
- WinRM disablement
- Network Discovery disablement
- File and Printer Sharing disablement
- Built-in Administrator and Guest account disablement
- Account lockout protection
- Validation artifact collection and version control

The Windows work emphasized practical hardening that improves security posture without making a daily-use personal system unnecessarily disruptive.

Windows phase status: Complete

See `windows/README.md` for details.

## Methodology

Each platform followed the same general workflow:

1. Collect a baseline
2. Apply hardening measures
3. Validate the resulting configuration
4. Store evidence artifacts
5. Commit the results to version control

This approach helps show not only what was changed, but also how the changes were verified.

## Scope Notes

This project is intended as a practical workstation hardening exercise and portfolio artifact.

It is not intended to represent:

- a full enterprise security baseline
- formal compliance against a framework
- exhaustive operating system lockdown

Where appropriate, usability and real-world daily-use considerations were weighed against stricter hardening options.

## Outcome

This repository represents a completed multi-platform endpoint hardening project with:

- documented Linux hardening work
- documented Windows hardening work
- preserved baseline and validation evidence
- practical security decisions based on system use case
- a repeatable assessment and hardening workflow

## Privacy Note

Some raw evidence files and environment-specific details were redacted or omitted in the public version of this repository to avoid exposing personal device, network, or account information. The public repo is intended to show the project methodology, hardening approach, and validation process without publishing unnecessary machine-specific data.

## Status

- Linux phase: Complete
- Windows phase: Complete
