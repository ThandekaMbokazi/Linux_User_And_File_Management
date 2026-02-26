# Operating Systems and You – Becoming a Power User
## Individual Practical Task: User & File Management Exercise

## Project Overview
This project simulates the real-world responsibilities of a System Administrator. The objective was to configure a secure, multi-user Ubuntu environment, manage granular file permissions, and handle software deployments using the Command Line Interface (CLI).

---

## 1. Advanced User & Group Lifecycle
Managing identities is the first line of defense in operating system security.

### **A. User Provisioning**
I initiated the environment by creating a dedicated user account. Unlike a simple user creation, the `adduser` utility in Ubuntu is a high-level tool that manages home directories and shell assignments automatically.
* **Action:** `sudo adduser student1`
* **Observation:** The system successfully allocated a Unique Identifier (UID) and created a localized environment for the user.

### User Creation Success
<img width="861" height="644" alt="image" src="https://github.com/user-attachments/assets/c396ef8e-6e5d-472b-bf14-095ac0afdadd" />


### **B. Administrative Privilege Escalation**
In Linux, the "Principle of Least Privilege" is vital. I created a custom group and managed the `sudoers` list to ensure users have exactly the power they need—no more, no less.
* **Task:** Created a `power_users` group for departmental organization.
* **Privilege:** Added `student1` to the `%sudo` group, allowing the user to perform administrative tasks without logging in as root.

### Group Creation
<img width="894" height="660" alt="image" src="https://github.com/user-attachments/assets/4ed3005c-4344-45f0-9b03-29d0781d6660" />

### Sudo Group Verification
<img width="896" height="631" alt="image" src="https://github.com/user-attachments/assets/97d32fdc-3939-462c-bf87-3f067c4fc8b4" />


### **C. Hardening via Password & Account Policies**
A "Power User" must know how to automate security. I implemented account aging policies to mitigate the risk of compromised credentials.
* **Password Aging:** Forced a 90-day rotation using `sudo chage -M 90`.
* **Account Deactivation:** Set a hard expiration date for the account to ensure access is revoked automatically after the project ends.

### Security Policies
<img width="1031" height="632" alt="image" src="https://github.com/user-attachments/assets/eada6efe-87e8-4eaa-930d-1ceea60f084f" />


---

## 2. File System Architecture & Security

### **A. Directory Hierarchy Construction**
I established a structured workspace to test file system interactions. Understanding where files live in the Linux tree is essential for effective management.
* **Setup:** Created a directory `project_files` and a sensitive `report.txt`.

### File Creation
<img width="904" height="638" alt="image" src="https://github.com/user-attachments/assets/10654779-31cc-4b49-beb6-9c0ebfa17153" />


### **B. Ownership Transfer & Permission Masks**
This task demonstrated the transition of data ownership and the application of numeric permission masks.
* **Ownership:** Shifted the file's primary owner and group to `student1`.
* **Permissions:** Applied a `600` (rw-------) mask, ensuring that only the owner can read or write to the file, protecting it from other users on the system.

> ** Troubleshooting Insight:** > During the exercise, I deliberately documented a "Permission Denied" error. This serves as a critical learning point: even with the correct command syntax, the OS enforces strict security. Without `sudo` (SuperUser Do), the system protects files from unauthorized modification.

### Ownership Change
<img width="844" height="677" alt="image" src="https://github.com/user-attachments/assets/96834b1a-c1e5-4b43-b7ad-0d8c33777b5a" />

### Permission Error
<img width="859" height="650" alt="image" src="https://github.com/user-attachments/assets/7ac029fa-4450-4582-ab84-b5b568dae3d6" />



---

## 3. Package Management & System Utilities

### **A. APT Package Deployment**
The Advanced Package Tool (APT) is the backbone of Ubuntu software management. I demonstrated the ability to update the local cache and install binary utilities.
* **Installation:** Deployed the `tree` utility to provide a visual representation of the file system.

### Apt Install
<img width="948" height="492" alt="image" src="https://github.com/user-attachments/assets/89a5ea63-348a-40ab-a252-ae47ddc63ed0" />


### **B. Output Verification**
The installation was verified by generating a recursive directory tree, proving that the software is correctly mapped in the system's `$PATH`.

### Package Verification
<img width="1099" height="752" alt="image" src="https://github.com/user-attachments/assets/ddfa5018-0615-4f48-8f63-0a519332b622" />


---

## Learning Outcomes
Through this practical exercise, I have mastered:
1. **User Management:** The ability to create, modify, and expire accounts.
2. **Security Advocacy:** Implementing password complexity and aging via CLI.
3. **Permissions Mastery:** Using `chmod` and `chown` to secure sensitive data.
4. **Software Lifecycle:** Installing and verifying system packages using `apt`.

---

## Conclusion
This project successfully demonstrates the core competencies required to manage a Linux-based Operating System. By moving beyond a graphical interface and utilizing the Command Line, I have gained the ability to automate administrative tasks, enforce strict security protocols, and manage system resources efficiently. 

These skills are foundational for any IT Professional aiming to manage servers, cloud environments, or secure enterprise workstations.

---
