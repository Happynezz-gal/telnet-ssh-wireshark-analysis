# Examining Telnet and SSH in Wireshark

A documented cybersecurity lab comparing what Wireshark reveals during Telnet and SSH sessions. The lab demonstrates why encrypted SSH is preferred to Telnet for remote administration.

## Objectives
- Capture a Telnet session in Wireshark.
- Inspect Telnet traffic using the `telnet` display filter and **Follow → TCP Stream**.
- Capture an SSH session and inspect it using the `ssh` display filter.
- Compare the visibility of application data in both sessions.
- Record observations with screenshots and a short lab report.

## Lab environment
Follow the supplied Cisco NetAcad lab, **“Lab - Examining Telnet and SSH in Wireshark.”** It specifies the CyberOps Workstation VM and loopback (`lo`) interface. Use only your own authorized lab VM or systems you have permission to test.

## Repository map
```text
.
├── README.md
├── .gitignore
├── LICENSE
├── docs/
│   ├── lab-report.md
│   ├── workflow.md
│   └── troubleshooting.md
├── evidence/
│   ├── screenshots/
│   ├── captures/
│   └── notes/
├── references/
│   └── references.md
└── scripts/
    └── README.md
```

## Workflow
1. Prepare the lab VM and confirm Wireshark, Telnet client/service, and SSH are available.
2. Capture a Telnet session on `lo`; use the `telnet` display filter and follow the TCP stream.
3. Capture an SSH session on `lo`; use the `ssh` display filter and follow the TCP stream.
4. Save sanitized screenshots to `evidence/screenshots/`.
5. Complete `docs/lab-report.md` with your own observations and reflection.
6. Review files for passwords, tokens, private keys, public IPs, or other sensitive data before committing.
7. Commit and push the documentation to GitHub using Git Bash.

## Important evidence hygiene
- **Never commit passwords, private keys, tokens, or unredacted sensitive packet captures.**
- The Telnet lab may expose entered credentials in plaintext. Do not include those credentials in screenshots, notes, or GitHub.
- Packet capture files (`.pcap`, `.pcapng`) are ignored by default. If you need to retain captures for assessment, keep them locally or use a private, access-controlled storage location approved by your instructor.
- Use screenshots that show the relevant finding while redacting credentials and unrelated personal information.

## Quick start (Git Bash)
```bash
git init
git add .
git status
git commit -m "Add Telnet and SSH Wireshark lab documentation"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/telnet-ssh-wireshark-analysis.git
git push -u origin main
```
Replace `YOUR-USERNAME` with your GitHub username. If the folder was cloned from GitHub already, do not run `git init` or add the remote again; use `git add .`, `git commit`, and `git push`.

## Suggested repository details
- **Repository name:** `telnet-ssh-wireshark-analysis`
- **Description:** `A documented Wireshark lab comparing Telnet plaintext traffic with encrypted SSH traffic, including workflow notes, sanitized screenshots, and security observations.`

## Expected conclusion
Telnet does not encrypt session contents, so sensitive data may be readable in a packet capture. SSH encrypts session traffic, making captured application contents unreadable without appropriate session keys. SSH also supports host authentication and integrity protections. Encryption does not make every SSH configuration automatically secure; use strong authentication and current configurations.

## Progress checklist
- [ ] Telnet capture inspected
- [ ] SSH capture inspected
- [ ] Screenshots saved and sanitized
- [ ] Lab report completed
- [ ] Reflection question answered
- [ ] Repository reviewed for secrets
- [ ] Changes pushed to GitHub
