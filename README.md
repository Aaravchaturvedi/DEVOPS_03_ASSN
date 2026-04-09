# DEVOPS_03_ASSN

# 🐧 DEVOPS Assignment – Linux System Administration

## 👨‍💻 Author

**Aarav Chaturvedi**

---

## 📌 Objective

This assignment demonstrates core Linux system administration tasks including:

* System auditing
* User monitoring
* Group management
* User onboarding
* System information analysis

---

# 🧾 PART 1: Initial System Audit

---

## 🔹 1. Check identity of current user

### Command:

```bash
whoami
```

### Output:

```bash
aarav
```

---

## 🔹 2. Display username of current session

### Command:

```bash
logname
```

### Output:

```bash
logname: no login name
```

---

## 🔹 3. Check logged-in users

### Command:

```bash
who
```

### Output:

```bash
aarav    pts/1        2026-04-09 10:55
```

---

## 🔹 4. Display what users are doing

### Command:

```bash
w
```

### Output:

```bash
11:03:05 up 59 min,  1 user,  load average: 0.00, 0.08, 0.17
USER     TTY      FROM   LOGIN@   IDLE   JCPU   PCPU  WHAT
aarav    pts/1    -      10:55    7:35   0.03s  0.03s -bash
```

---

## 🔹 5. View login history

### Command:

```bash
last
```

### Output (truncated):

```bash
reboot   system boot  6.6.87.2-microso Thu Apr  9 10:55   still running
reboot   system boot  6.6.87.2-microso Thu Apr  9 10:46   still running
...
wtmp begins Sat Jul  5 14:26:58 2025
```

---

## 🔹 6. Display complete system information

### Command:

```bash
uname -a
```

### Output:

```bash
Linux DESKTOP-KL7Q27N 6.6.87.2-microsoft-standard-WSL2 #1 SMP PREEMPT_DYNAMIC Thu Jun  5 18:30:46 UTC 2025 x86_64 x86_64 x86_64 GNU/Linux
```

---

## 🔹 7. Display hostname

### Command:

```bash
hostname
```

### Output:

```bash
DESKTOP-KL7Q27N
```

---

## 🔹 8. Check system uptime

### Command:

```bash
uptime
```

### Output:

```bash
11:03:30 up 59 min,  1 user,  load average: 0.00, 0.07, 0.16
```

---

# 🧾 PART 2: Department Setup

---

## 🔹 1. Create group "developers"

### Command:

```bash
sudo groupadd developers
```

---

## 🔹 2. Create group "qa"

### Command:

```bash
sudo groupadd qa
```

---

## 🔹 3. Verify groups created

### Command:

```bash
getent group developers
getent group qa
```

### Expected Output:

```bash
developers:x:1001:
qa:x:1002:
```

---

## 🔹 4. Display all groups

### Command:

```bash
cut -d: -f1 /etc/group
```

---

# 🧾 PART 3: Employee Onboarding

---

## 🔹 1. Create users

### Command:

```bash
sudo useradd -m aman
sudo useradd -m ritu
sudo useradd -m karan
```

---

## 🔹 2. Set passwords

### Command:

```bash
sudo passwd aman
sudo passwd ritu
sudo passwd karan
```

---

## 🔹 3. Assign users to departments

### Command:

```bash
sudo usermod -aG developers aman
sudo usermod -aG developers ritu
sudo usermod -aG qa karan
```

---

## 🔹 4. Verify user-group mapping

### Command:

```bash
groups aman
groups ritu
groups karan
```

### Expected Output:

```bash
aman : aman developers
ritu : ritu developers
karan : karan qa
```

---

# 🎯 Final Outcome

✔ System audit completed
✔ Groups created successfully
✔ Users onboarded correctly
✔ Proper group assignments verified

---

# 💡 Key Learnings

* `whoami` → current user
* `who` vs `w` → login vs activity
* `groupadd` → create groups
* `useradd` → create users
* `usermod -aG` → assign groups
* `/etc/group` → group database

---

# 🔥 Conclusion

This assignment successfully demonstrates real-world Linux administration tasks including system monitoring, user management, and group-based access control in a development environment.

---
