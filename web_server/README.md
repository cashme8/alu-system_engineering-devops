Paraphrased Text:

# Web Server

![Web Server Block Diagram](https://www.keil.com/pack/doc/mw/Network/html/http_server_block_diagram.png)

Web servers are composed of both hardware and software that utilize the Hypertext Transfer Protocol (HTTP) to respond to requests from web users on the World Wide Web.

__NOTE:__ For this project, certain tasks will be evaluated based on two criteria:

1. Is your web-01 server configured as per the requirements?
2. Does your answer file include a Bash script that can automatically execute commands to configure an Ubuntu machine to meet the requirements, without any manual intervention?

## Learning Objectives

A proficient software engineer is often characterized as a lazy one, believe it or not.

![Lazy Software Engineer](https://s3.amazonaws.com/intranet-projects-files/holbertonschool-sysadmin_devops/266/82VsYEC.jpg)

__General Objectives__
	- Understanding the primary role of a web server
	- Definition of a child process
	- Rationale behind the presence of parent and child processes in web servers
	- Familiarity with main HTTP requests

__DNS__
	- Decoding the acronym DNS
	- Grasping the primary role of DNS

__DNS Record Types__
	- `A Records`
	- `CNAME`
	- `TXT Records`
	- `MX Records`

- Insight into how the web functions
- Understanding of `Nginx`
- Configuration of `Nginx`
- Concept of Child processes
- Understanding of __Root and sub-domain__
- `HTTP` __requests__
- `HTTP` __redirection__
- Handling the Not found `HTTP` response code
- Linux log files
- Understanding of `HTTP/1.1` and `HTTP/2`
- Usage of `scp` and `curl`

## Requirements

__General__

- Permitted editors: `vi`, `vim`, `emacs`
- Interpretation on `Ubuntu 16.04 LTS`
- All files should end with a new line
- Presence of a mandatory `README.md` file at the project folder's root
- All Bash script __files must be executable__
- Bash scripts must pass `Shellcheck (version 0.3.7)` without errors
- The first line of Bash scripts should be `#!/usr/bin/env bash`
- The second line should be a comment explaining the script's purpose
- Prohibition of using `systemctl` for process restart
- Basic knowledge of Bash scripting required

## Video Tutorial

For a step-by-step guide on installation and configuration, click the __"watch video"__ link to get started.

- Access the video tutorial -> [Watch Video](https://youtu.be/5vy448hK-c4)

## Installing Required Packages

```bash

$ sudo apt-get install shellcheck -y

# Check shellcheck version

$ shellcheck -V

# Installing nginx

$ sudo apt-get install nginx -y

```

## Configuring Nginx

```bash

# Configuring the default file

$ sudo vi /etc/nginx/sites-available/default

# Once the vi editor opens

server {
  listen 80 default_Server;
  root /var/www/html;
  index index.html index.htm index.nginx-debian.html;

# if you have a domain name replace '_' with it
  server_name _;

# configuring error_page
  error_page 404 404.html;

  location / {
	try_files $uri $uri/ =404;
  }

  location = /404.html {
	internal;
  }
}

```
