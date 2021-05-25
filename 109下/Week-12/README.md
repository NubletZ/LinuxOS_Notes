# LINUX WEEK 12 (05-25-2021)
## Notes
### Processes
Process is a program that is curently running in your computer. It exist in parent-chiled hierarchies. There are several types of process in linux.

### Foreground and Background Process
A foreground is a process that refer to application which currently running and is interacting with the user. While the background processes refer to those application which run independently and not interacting with user.

### Daemon Process
A daemon process is a process that usualy start running when the system is bootstraped and will terminated on system shut down. The user doesn't have a direct control for this process.

### Zombie Process
A zombie process actualy is a process that is no longer executing, but it continue to exist in the process table until its parent dies or until the system is shut down.

## Command
### 1). List all processes of all users
To list all processes of all users can type the command `$ ps -ef` or `$ ps -aux`. You can also use this command to see the PID of specific process. For example type the following command and you'll be able to see the sshd PID

```
$ ps -aux | grep sshd
```

### 2). Show the whole process in system
The command `$ pstree` will show the whole process in the system and it will show the relation between parent system and the child system. In Linux you will find that the whole process parent is `systemd` and if you check its PID is 1. Here is the example of the output :

<img src="pstree.PNG" alt="pstree" title="pstree" width="900" />

### 3). Kill program
For a program that running normaly you can simply kill it by typing the following command :

```
$ kill [PID]
```

but if the program become a zombie process then we need to add parameter `-9` in our program to force close it.

```
$ kill -9 [PID]
```

### 4). nice and renice
In a system if there are several process is running, a CPU will run it based on its priorities value. This priority value can be set by using `nice` or `renice` command to set again its priority value

<img src="nicerenice.PNG" alt="Nice and Renice" title="Nice and Renice" width="900" />