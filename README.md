# Awesome Windows Security

A community-curated list of tools for securing Windows systems in production, enterprise, and lab environments.

No dead repos. No theory without working code. Every tool here solves one specific Windows security task.

## Categories

- [Hardening & Compliance](#hardening--compliance)
- [Microsoft Defender](#microsoft-defender)
- [Identity & Access (AD/AAD)](#identity--access-adaad)
- [Logging & Detection](#logging--detection)
- [Offensive Testing (Blue Team only)](#offensive-testing-blue-team-only)

## Hardening & Compliance

Tools that apply, verify, or roll back Windows security configurations.

- **DCAT (Defender Control and Audit Toolkit)** – Production-safe hardening with one-click rollbacks and HTML/JSON compliance reports. `Invoke-DCAT -preset paranoid`
- **Harden Windows Safely** – Community script using official Microsoft methods. Locks systems from Personal to Military levels. `.\Hardening.ps1 -level Government`
- **LGPO** – Microsoft's official tool to import/export local security policies without GUI. `LGPO.exe /g policybackup\ /s`
- **Multron Win Care** – GUI for Defender, Firewall, and telemetry on Windows 10/11.

## Microsoft Defender

Tools that configure, extend, or audit Microsoft Defender.

- **DefenderUI** – Unlocks hidden Defender settings including ASR rules and cloud protection levels.
- **ConfiguringDefender** – PowerShell module to manage Defender via Intune or local policy. `Set-DefenderASR -BlockOfficeMacros $true`
- **DefendNot** – Temporarily disables Defender for lab testing. Requires reboot rollback. `defendnot.exe --disable --duration 2h`

## Identity & Access (AD/AAD)

Tools for auditing Active Directory, Azure AD, Kerberos, and local authentication.

- **BloodHound** – Attack path mapping for Active Directory. `SharpHound.exe -c All`
- **PingCastle** – Fast AD health and security assessment with risk scoring. `PingCastle.exe --healthcheck --server dc.prod.local`
- **PurpleKnight** – Detects AD misconfigurations that lead to privilege escalation.
- **Rubeus** – Kerberos attack toolkit in C#. `Rubeus.exe asktgt /user:admin /password:pass`

## Logging & Detection

Tools that collect, parse, or analyze Windows Event Logs, ETW, and Sysmon data.

- **Sysmon** – Microsoft's system activity monitoring driver. Use with Olaf Hartong's sysmon-config.
- **Hayabusa** – Sigma rule engine for Windows event logs. `hayabusa.exe csv-timeline -d logs/ -o timeline.csv`
- **DeepBlueCLI** – Hunts attack patterns in exported event logs. `powershell -exec bypass .\DeepBlue.ps1 .\security.evtx`

## Offensive Testing (Blue Team only)

Tools to validate Windows defenses. Do not use on systems you do not own.

- **Mimikatz** – Credential extraction from Windows memory. `privilege::debug` `sekurlsa::logonpasswords`


Rules:

- Tool must be Windows-specific
- Last commit must be less than 24 months old
- No paid tools without a free tier
- No wrappers that add nothing new

Pull requests are reviewed within 7 days. If rejected, you will get a clear reason.

## Why this list exists

General security lists are too broad. Windows-specific lists are outdated. This repo is maintained by people who actually run Windows security.

## License

CC0 – use any part of this list without asking.
- **Seatbelt** – Host enumeration for security assessments. `Seatbelt.exe -group=system`

