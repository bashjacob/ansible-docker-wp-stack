# WordPress Docker deployment with Ansible

This project provides a simple way to deploy WordPress with MariaDB using Docker containers, automated with Ansible.

## Setup Instructions

### 1. Prepare your environment

- Make sure you have ansible already installed on your machine
- Make sure you don't have any troubles with your ec2 instance connection

### 2. Configure the deployment

- Edit the `inventory.ini` file to include your server ip address and ssh details
- Edit the `secrets.yml` with your desired database credentials (don't forget about ansible-vault!)

### 3. Run the deployment

```bash
ansible-playbook -i inventory.ini deploy.yml
```

### 4. Access your WordPress!

Once deployment is complete, access your WordPress site by visiting your server's ip address in a web browser (using http port(80)).

## Troubleshooting

### WordPress Not Loading

Check if containers are running:
```bash
cd /opt/wordpress && docker-compose ps
```

View logs:
```bash
cd /opt/wordpress && docker-compose logs <container_name>
```

### Database Connection Issues

Verify the environment variables:
```bash
cat /opt/wordpress/.env
```
