# Practical workflow: Telnet vs SSH in Wireshark

## 1. Prepare the lab
- Start the CyberOps Workstation VM described by the course lab.
- Open Wireshark and select the loopback interface (`lo`).
- Confirm you are working only in the authorized lab environment.
- Create a folder on your computer for temporary capture files; keep raw captures out of Git.

## 2. Telnet capture
1. Start capturing on `lo`.
2. In a second terminal, connect to the lab's localhost Telnet service as described in the course handout.
3. Stop the capture after the test session.
4. Apply the display filter `telnet`.
5. Right-click a Telnet packet and select **Follow → TCP Stream**.
6. Observe whether the session content is readable. The course lab warns that credentials can appear in plaintext.
7. Close the stream and exit the Telnet session.
8. Take a screenshot that demonstrates the finding, with all credentials and sensitive details redacted.

## 3. SSH capture
1. Start a new capture on `lo`.
2. Connect to localhost over SSH as described in the course handout.
3. Stop the capture.
4. Apply the display filter `ssh`.
5. Right-click an SSH packet and select **Follow → TCP Stream**.
6. Compare the stream with Telnet. SSH application data should be encrypted and not readable as plaintext.
7. Save a sanitized screenshot.

## 4. Evidence checklist
- `evidence/screenshots/01-telnet-filter.png`
- `evidence/screenshots/02-telnet-stream-redacted.png`
- `evidence/screenshots/03-ssh-filter.png`
- `evidence/screenshots/04-ssh-stream.png`
- Completed `docs/lab-report.md`

Screenshots above are suggested filenames; add your own evidence. Never put real passwords in screenshots or Markdown. Keep raw `.pcap`/`.pcapng` files local and ignored.

## 5. Validate and publish
From Git Bash in the repository directory:
```bash
git status
git diff --check
git add README.md .gitignore LICENSE docs evidence references scripts
git status
git commit -m "Document Telnet and SSH Wireshark comparison"
git push
```
Review `git status` carefully before committing. If a capture file appears staged, unstage it with `git restore --staged path/to/file` and remove it from the repository directory if it should remain private.
