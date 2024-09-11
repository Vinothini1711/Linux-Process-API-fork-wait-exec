# Linux-Process-API-fork-wait-exec-
Ex02-Linux Process API-fork(), wait(), exec()
# Ex02-OS-Linux-Process API - fork(), wait(), exec()
Operating systems Lab exercise


# AIM:
To write C Program that uses Linux Process API - fork(), wait(), exec()

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Write the C Program using Linux Process API - fork(), wait(), exec()

### Step 3:

Test the C Program for the desired output. 

# PROGRAM:

## C Program to print process ID and parent Process ID using Linux API system calls
```
#include <stdio.h>
#include <sys/types.h>
#include <unistd.h>
int main(void)
{	//variable to store calling function's process id
	pid_t process_id;
	//variable to store parent function's process id
	pid_t p_process_id;
	//getpid() - will return process id of calling function
	process_id = getpid();
	//getppid() - will return process id of parent function
	p_process_id = getppid();
	//printing the process ids

//printing the process ids
	printf("The process id: %d\n",process_id);
	printf("The process id of parent function: %d\n",p_process_id);
	return 0; }

```




##OUTPUT


![Screenshot 2024-09-11 111632](https://github.com/user-attachments/assets/7137034a-d025-43aa-ae67-d4de10844633)

![Screenshot 2024-09-11 111648](https://github.com/user-attachments/assets/9c08797b-013d-4a8f-97be-008d55c8f276)

![Screenshot 2024-09-11 111659](https://github.com/user-attachments/assets/5776dc66-3acd-49f7-a23b-1a34113ff3b3)


## C Program to create new process using Linux API system calls fork() and exit()
![Screenshot 2024-09-11 111719](https://github.com/user-attachments/assets/b32a0292-4dc4-4705-81a6-1765032ca6d8)


##OUTPUT


![Screenshot 2024-09-11 111728](https://github.com/user-attachments/assets/ccc162d5-262c-4bcf-bf09-fb4af0867790)






## C Program to execute Linux system commands using Linux API system calls exec() family
```
#include<stdio.h>
#include<unistd.h>
#include <stdlib.h>
#include <sys/wait.h>
#include <sys/types.h>
int main()
{       int status;
        printf("Running ps with execlp\n");
        execl("ps", "ps", "ax", NULL);
        wait(&status);
        if (WIFEXITED(status))
                printf("child exited with status of %d\n", WEXITSTATUS(status));
        else
                puts("child did not exit successfully\n");
        printf("Done.\n");
printf("Running ps with execlp. Now with path specified\n");
        execl("/bin/ps", "ps", "ax", NULL);
        wait(&status);
        if (WIFEXITED(status))
                printf("child exited with status of %d\n", WEXITSTATUS(status));
        else
                puts("child did not exit successfully\n");
        printf("Done.\n");
        exit(0);}

```


























##OUTPUT

![Screenshot 2024-09-11 111737](https://github.com/user-attachments/assets/2ecdb18d-4ab9-4191-9a6d-c80ef02fb9fc)



# RESULT:
The programs are executed successfully.
