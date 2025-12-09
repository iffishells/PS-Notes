Here are the **corrected and cleanly formatted versions** of your screen-session–killing commands.

---

# Commands

### **1. Kill *detached* screen sessions using `screen -X quit`**

```bash
screen -ls | awk '/Detached/ {print $1}' | xargs -r -I {} screen -S {} -X quit
```

### **2. Kill *detached* screen sessions using `kill -9`**

> (Extract only the PID before the dot)

```bash
screen -ls | awk '/Detached/ {print $1}' | cut -d. -f1 | xargs -r kill -9
```

### **3. (Same as #2, cleaned formatting)**

```bash
screen -ls | awk '/Detached/ {print $1}' | cut -d. -f1 | xargs -r kill -9
```

---

