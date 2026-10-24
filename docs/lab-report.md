# Lab report: Examining Telnet and SSH in Wireshark

## 1. Aim
Compare the visibility of Telnet and SSH session data in Wireshark.

## 2. Environment
- VM / operating system:
- Wireshark version:
- Capture interface:
- Date performed:

## 3. Method
Summarize the steps you performed for the Telnet and SSH captures. Do not include credentials.

## 4. Findings

### Telnet
- Display filter used: `telnet`
- What was visible in the packet list?
- What did **Follow → TCP Stream** reveal?
- Evidence screenshot(s):

### SSH
- Display filter used: `ssh`
- What was visible in the packet list?
- What did **Follow → TCP Stream** reveal?
- Evidence screenshot(s):

## 5. Comparison

| Property | Telnet | SSH |
|---|---|---|
| Session contents encrypted? | No | Yes |
| Application data readable in stream? | Often readable as plaintext | Normally unreadable without session keys |
| Suitable for secure remote administration? | No | Yes, with secure configuration |

Add your own observations and note any differences in your capture.

## 6. Reflection question
**Why is SSH preferred over Telnet for remote connections?**

Write your answer here. Address encryption, confidentiality, and the risk of exposing credentials or commands.

## 7. Evidence index
| Evidence file | What it demonstrates |
|---|---|
| `evidence/screenshots/01-telnet-filter.png` | Telnet packets selected with display filter |
| `evidence/screenshots/02-telnet-stream-redacted.png` | Telnet stream observation with sensitive data redacted |
| `evidence/screenshots/03-ssh-filter.png` | SSH packets selected with display filter |
| `evidence/screenshots/04-ssh-stream.png` | SSH stream observation |

Replace these example entries with the screenshots you actually captured.

## 8. Lessons learned
- 
- 

## 9. Limitations
Describe anything that did not work, services that were unavailable, or differences in your environment.
