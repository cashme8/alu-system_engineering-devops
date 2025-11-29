# Web stack debugging #0

**Table:**
```html
<table>
    <tr>
        <td>DevOps</td>
        <td>SysAdmin</td>
        <td>Scripting</td>
        <td>Debugging</td>
    </tr>
</table>
```

**Table:**
```html
<table>
    <tr>
        <td>By: Sylvain Kalache, co-founder at Holberton School</td>
    </tr>
    <tr>
        <td>Weight: 1</td>
    </tr>
    <tr>
        <td>Project will start Jan 2, 2024 6:00 AM, must end by Jan 4, 2024 6:00 AM</td>
    </tr>
    <tr>
        <td>Checker will be released at Jan 3, 2024 6:00 PM</td>
    </tr>
    <tr>
        <td>An auto review will be launched at the deadline</td>
    </tr>
</table>
```

## Concepts
<i>For this project, we expect you to look at these concepts:</i>

- Network basics
- Docker
- Web stack debugging

<img align="center" alt="I love Debugging" width="600" src="debugging.jpg" />

## Background Context
The Webstack debugging series aims to train you in the art of debugging. Computers and software rarely work the way we want (that’s the “fun” part of the job!).

Debugging a webstack is essential for a Full-Stack Software Engineer, and it takes practice to master it.

In this debugging series, you will be given broken/bugged webstacks. The final goal is to create a Bash script that, when executed, brings the webstack to a working state. But before writing this Bash script, you should figure out what is going on and fix it manually.

Let’s start with a simple example. My server must:

- Have a copy of the /etc/passwd file in /tmp
- Have a file named /tmp/isworking containing the string OK

Let’s pretend that without these 2 elements, my web application cannot work.

Let’s go through this example and fix the server.

```bash
vagrant@vagrant:~$ docker run -d -ti ubuntu:14.04
Unable to find image 'ubuntu:14.04' locally
...
root@76f44c0da25e:/# ls /tmp/
root@76f44c0da25e:/# cp /etc/passwd /tmp/
root@76f44c0da25e:/# echo OK > /tmp/isworking
root@76f44c0da25e:/# ls /tmp/
isworking  passwd
root@76f44c0da25e:/#
vagrant@vagrant:~$
```

Then my answer file would contain:

```bash
sylvain@ubuntu:~$ cat answerfile
#!/usr/bin/env bash
# Fix my server with these magic 2 lines
cp /etc/passwd /tmp/
echo OK > /tmp/isworking
sylvain@ubuntu:~$
```

Note that as you cannot use interactive software such as emacs or vi in your Bash script, everything needs to be done from the command line (including file edition).

## Installing Docker
For this project, you will be given a container that you can use to solve the task. If you would like to have Docker to experiment with and/or solve this problem locally, you can install it on your machine, your Ubuntu 14.04 VM, or your Ubuntu 16.04 VM if you upgraded.

- Mac OS
- Windows
- Ubuntu 14.04 (Note that Docker for Ubuntu 14 is deprecated and you will have to make some adjustments to the instructions when installing)
- Ubuntu 16.04

## Resources
### man or help:
- curl

## Requirements
### General
- Allowed editors: vi, vim, emacs
- All your files will be interpreted on Ubuntu 14.04 LTS
- All your files should end with a new line
- A README.md file, at the root of the folder of the project, is mandatory
- All your Bash script files must be executable
- Your Bash scripts must pass Shellcheck without any error
- Your Bash scripts must run without error
- The first line of all your Bash scripts should be exactly `#!/usr/bin/env bash`
- The second line of all your Bash scripts should be a comment explaining what is the script doing

## Tasks
### 0. Give me a page!
```bash
score
```
Be sure to read the Docker concept page.

In this first debugging project, you need to get Apache to run on the container and return a page containing "Hello Holberton" when querying the root of it.

<i>Example:</i>
```bash
vagrant@vagrant:~$ docker run -p 8080:80 -d -it holbertonschool/265-0
...
vagrant@vagrant:~$ docker ps
...
vagrant@vagrant:~$ curl 0:8080
curl: (52) Empty reply from server
vagrant@vagrant:~$
```
After connecting to the container and fixing whatever needed to be fixed (here is your mission), you can see that curling port 80 returns a page that contains "Hello Holberton." Paste the command(s) you used to fix the issue in your answer file.
