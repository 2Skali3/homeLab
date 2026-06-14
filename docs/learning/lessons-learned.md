# Lessons Learned

## 2026-06-14 Sunday - Foundation Audit

### Documentation Must Be Verified

Initial documentation listed the production server CPU as an Intel T6600.

Hardware auditing confirmed the actual CPU is an Intel Core2 Duo P7350.

Lesson:

Assumptions should be verified through evidence collection rather than copied forward indefinitely.

---

### Backups Are More Important Than Capacity

The production server had significant unused storage capacity but no backup strategy.

Lesson:

Recoverability is more important than available storage space.

---

### Security and Recoverability Are Different Problems

The server had:

- SSH key authentication
- Fail2ban
- UFW firewall
- Locked root account

Despite this, complete data loss remained possible because backups did not exist.

Lesson:

A secure system is not necessarily a recoverable system.