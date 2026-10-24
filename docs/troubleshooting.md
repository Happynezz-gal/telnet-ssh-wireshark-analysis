# Troubleshooting

- **No packets appear:** confirm the capture is running on `lo` and that the test connection uses localhost.
- **No Telnet traffic:** check whether the lab VM's Telnet service is enabled and reachable; do not enable services on systems you do not administer.
- **No SSH traffic:** confirm the SSH service is available in the lab VM and that the connection succeeds.
- **Filter shows nothing:** try `tcp` to inspect whether traffic exists, then verify the correct service/port and use the `telnet` or `ssh` display filter as appropriate.
- **Cannot push to GitHub:** verify the remote with `git remote -v`, confirm you are signed in / authenticated, and check repository permissions.
- **Accidentally staged a capture:** run `git restore --staged path/to/file`, then ensure the capture remains ignored and is not committed.
- **A secret was committed:** deleting it in a later commit does not remove it from history. Treat it as exposed, rotate/revoke it, and follow GitHub's sensitive-data removal guidance.
