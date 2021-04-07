## Week 6 Homework Submission File: Advanced Bash - Owning the System

Please edit this file by adding the solution commands on the line below the prompt. 

Save and submit the completed file for your homework submission.

**Step 1: Shadow People** 

1. Create a secret user named `sysd`. Make sure this user doesn't have a home folder created:
    - `sudo useradd sysd`

2. Give your secret user a password: 
    - `sudo passwd sysd`

3. Give your secret user a system UID < 1000:

    - `sudo usermod -g 400 sysd`

4. Give your secret user the same GID:
  
  - `sudo groupmod -g 400 sysd`

5. Give your secret user full `sudo` access without the need for a password:
    - `sudo visudo`
   - Once the visudo file is open, pasted `sysd ALL=(ALL:ALL) NOPASSWD:ALL` under root

6. Test that `sudo` access works without your password:

    ```bash
    Matching Defaults entries for sysd on scavenger-hunt:
        env_reset, exempt_group=sudo, mail_badpass,
        secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

    User sysd may run the following commands on scavenger-hunt:
        (ALL : ALL) NOPASSWD: ALL
    ```

**Step 2: Smooth Sailing**

1. Edit the `sshd_config` file:
 - Adding ports to the SSH for connection by editing the sshd_config
 `sudo nano /etc/ssh/sshd_config`
    ```bash
    Port 22
    Port 2222
    ```

**Step 3: Testing Your Configuration Update**
1. Restart the SSH service:
    - `Your solution command here`

2. Exit the `root` account:
    - `Your solution command here`

3. SSH to the target machine using your `sysd` account and port `2222`:
    - `Your solution command here`

4. Use `sudo` to switch to the root user:
    - `Your solution command here`

**Step 4: Crack All the Passwords**

1. SSH back to the system using your `sysd` account and port `2222`:

    - `Your solution command here`

2. Escalate your privileges to the `root` user. Use John to crack the entire `/etc/shadow` file:

    - `Your solution command here`

---

© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.

