### **✅ Redis Configuration Manipulation via CLI – Checklist**  

This checklist helps you manage the **Redis configuration** directly from the **command-line interface (CLI)** without editing `redis.conf` manually. It is divided into **RDB (Redis Database) Snapshotting** and **AOF (Append-Only File) Logging** sections.  

---

## **🟢 RDB (Snapshotting) Management via CLI**  

🔹 **1. Check Current RDB Settings**  
```bash
CONFIG GET save
CONFIG GET dbfilename
CONFIG GET dir
```

🔹 **2. Enable/Disable RDB Snapshots**  
- **Enable RDB Persistence (Default)**  
  ```bash
  CONFIG SET save "900 1 300 10 60 10000"
  ```
- **Disable RDB Persistence**  
  ```bash
  CONFIG SET save ""
  ```

🔹 **3. Manually Trigger RDB Snapshot**  
- **Blocking Snapshot**  
  ```bash
  SAVE
  ```
- **Background Snapshot**  
  ```bash
  BGSAVE
  ```

🔹 **4. Check Last RDB Save Time**  
```bash
LASTSAVE
```

🔹 **5. Change RDB Snapshot File Name or Directory**  
- **Change RDB File Name**  
  ```bash
  CONFIG SET dbfilename "dump-new.rdb"
  ```
- **Change Directory for Snapshots**  
  ```bash
  CONFIG SET dir "/new/path/to/snapshots/"
  ```

🔹 **6. Delete RDB Snapshot File**  
```bash
rm /var/lib/redis/dump.rdb
```

🔹 **7. Persist Runtime Changes to `redis.conf`**  
```bash
CONFIG REWRITE
```

---

## **🟠 AOF (Append-Only File) Management via CLI**  

🔹 **1. Check Current AOF Settings**  
```bash
CONFIG GET appendonly
CONFIG GET appendfilename
CONFIG GET appendfsync
CONFIG GET auto-aof-rewrite-percentage
```

🔹 **2. Enable/Disable AOF Persistence**  
- **Enable AOF Logging**  
  ```bash
  CONFIG SET appendonly yes
  ```
- **Disable AOF Logging**  
  ```bash
  CONFIG SET appendonly no
  ```

🔹 **3. Change AOF Filename or Directory**  
- **Change AOF File Name**  
  ```bash
  CONFIG SET appendfilename "custom.aof"
  ```
- **Change AOF Storage Directory**  
  ```bash
  CONFIG SET dir "/new/path/to/aof/"
  ```

🔹 **4. Change AOF Sync Policy (Performance vs. Durability Trade-off)**  
- **Sync on Every Write (Safest, Slowest)**  
  ```bash
  CONFIG SET appendfsync always
  ```
- **Sync Every Second (Balanced)**  
  ```bash
  CONFIG SET appendfsync everysec
  ```
- **Let OS Handle Syncing (Fastest, Risk of Data Loss)**  
  ```bash
  CONFIG SET appendfsync no
  ```

🔹 **5. Trigger AOF Rewrite to Reduce File Size**  
```bash
BGREWRITEAOF
```

🔹 **6. Delete AOF File (Caution: Data Loss!)**  
```bash
rm /var/lib/redis/appendonly.aof
```

🔹 **7. Persist Runtime Changes to `redis.conf`**  
```bash
CONFIG REWRITE
```