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


![Screenshot 2024-03-28 093016](https://github.com/ARCH2006/Linux-Process-API-fork-wait-exec/assets/144300030/4cc488e3-935b-4059-8eb0-a806618b2d57)

![Screenshot 2024-03-28 093121](https://github.com/ARCH2006/Linux-Process-API-fork-wait-exec/assets/144300030/600ea316-a73f-4a1b-983b-f58ea445aa43)


![Screenshot 2024-03-28 093141](https://github.com/ARCH2006/Linux-Process-API-fork-wait-exec/assets/144300030/3e37d025-e5ce-467c-be76-8ff6df26e2c7)










## C Program to create new process using Linux API system calls fork() and exit()



![Screenshot 2024-03-26 111936](https://github.com/ARCH2006/Linux-Process-API-fork-wait-exec/assets/144300030/e4568bde-1a35-438f-9a26-aecf564fb2c9)










##OUTPUT

![Screenshot 2024-03-26 111951](https://github.com/ARCH2006/Linux-Process-API-fork-wait-exec/assets/144300030/0471467c-2756-468b-9733-937002f9e4e4)







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

![Screenshot 2024-03-31 132809](https://github.com/ARCH2006/Linux-Process-API-fork-wait-exec/assets/144300030/484c81ce-b3aa-4741-811b-ae11bd29fcd5)



# RESULT:
The programs are executed successfully.
