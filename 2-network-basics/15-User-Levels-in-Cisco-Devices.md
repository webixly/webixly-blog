# **User Levels in Cisco Devices**

## **1. Introduction**

Cisco IOS uses a permission-based system called **User Levels** (or **Privilege Levels**) to control what commands a user can run on a device. This helps secure routers and switches by restricting sensitive configurations.

Cisco provides **16 privilege levels (0–15)**, where:

* **Level 0** → Almost no access
* **Level 1** → Basic user EXEC mode
* **Level 15** → Full administrative control (privileged EXEC / enable mode)
* **Levels 2–14** → Customizable levels for organizations

---

## **2. Default Privilege Levels**

### **Level 0 — Restricted**

Users can only run extremely limited commands:

* `logout`
* `enable`
* `disable`
* `ping`
* `traceroute`

This level is almost never used in real networks.

### **Level 1 — User EXEC Mode**

The default level for normal users when they login.
Users can:

* View basic system information
* Run diagnostic commands like `ping`, `show interfaces`
* View configurations but **cannot modify anything**

Prompt example:

```
Router>
```

### **Level 15 — Privileged EXEC (Enable Mode)**

The administrator level.
Users can:

* Enter configuration mode
* Modify the running config
* Manage interfaces, routing, ACLs
* Control system operations

Prompt example:

```
Router#
```

---

## **3. Custom Privilege Levels (2–14)**

Cisco allows assigning specific commands to custom privilege levels.
This is useful for:

* Junior network technicians
* Monitoring teams
* Security teams

### **Example: Assigning a Command to Privilege Level 5**

```
Router(config)# privilege exec level 5 show running-config
```

This allows level 5 users to run `show running-config`.

### **Creating a User with Custom Privilege 5**

```
Router(config)# username tech privilege 5 secret StrongPass123
```

---

## **4. Checking User Levels**

Use:

```
show privilege
```

Output example:

```
Current privilege level is 1
```

---

## **5. Moving Between Privilege Levels**

To elevate access:

```
Router> enable 5
```

To return to level 1:

```
Router# disable
```

---

## **6. Best Practices**

* Use level **15** only for trusted admins.
* Assign **custom privilege levels** for operational staff.
* Use **AAA (TACACS+/RADIUS)** for enterprise environments.
* Use **strong encrypted passwords** (never plain-text).
* Apply **role-based access control (RBAC)** when possible.

---

## **7. Summary Table**

| Level | Access Type | Description                       |
| ----- | ----------- | --------------------------------- |
| 0     | Restricted  | Minimal commands                  |
| 1     | User EXEC   | Basic show & diagnostic commands  |
| 2–14  | Custom      | Organization-specific permissions |
| 15    | Admin       | Full device control               |

---

