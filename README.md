# Ansible Nginx Setup

This project sets up a simple configuration using Ansible to install and start Nginx on a slave EC2 instance from a master EC2 instance.

## Prerequisites

- Two EC2 instances (one master and one slave) running Ubuntu.
- Ansible installed on both EC2 instances.
- Passwordless SSH configured between the master and slave instances.

## Steps

1. **Create EC2 Instances**:
   - Launch two Ubuntu EC2 instances (master and slave).

2. **Install Ansible**:
   - SSH into both instances and install Ansible using `sudo apt install -y ansible`.

3. **Configure Passwordless SSH**:
   - On the master instance, generate SSH keys using `ssh-keygen`.
   - Copy the public key to the slave instance using `ssh-copy-id`.

4. **Configure Ansible**:
   - Create an inventory file `inventory` with the slave instance's IP.
   - Write an Ansible playbook `nginx-playbook.yml` to install and start Nginx.

5. **Execute the Playbook**:
   - SSH into the master instance and run:
     ```bash
     ansible-playbook -i inventory nginx-playbook.yml
     ```

## Additional Information

- Make sure security groups on AWS allow SSH and HTTP traffic.
- Modify the playbook and inventory file as needed for different configurations.
