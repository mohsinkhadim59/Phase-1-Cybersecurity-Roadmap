# 📓 Day 10

**Focus:** TASK NAME

## Tasks
- [ ] Task 1
- [ ] Task 2

## Findings
- Command(s): 
- Notes: 
```bash
[ you / shell ]
      |
      |  printf "password\n"  (stdin)
      v
+----------------------+        TLS handshake       +----------------------+
|   ncat (client)      | <------------------------> |  Service (server)    |
|  --ssl localhost:30001|                           |  listening on :30001  |
+----------------------+                           +----------------------+
      |  ^                                                 |
      |  |  encrypted application data stream              |
      v  |                                                 v
[ TCP socket: 127.0.0.1:random > 127.0.0.1:30001 ]    [ server process reads ]

```

## Reflections
- What I learned today:
- What needs review:
[Cheatsheet-Tree](Cheatsheet-Tree.md) 🔗
