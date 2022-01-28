There are 3 kindes of permission in Linux:

1. **Read**: Allows a user to opern and read the file
2. **Write**: Allows a user to open and modify the file
3. **Execute** Allows a user to run the file

You can change the prmission of a file or a directory using the **_chmod_** command:
1. Symbolic mode
2. Absoulte mode

### Symbolic mode
```
$ chmod <targe>(+/-/=)<permission> <filename>
```
<target> can be u:user; g:group; o:other; a:all

- '+' is used for adding permission
- '-' is used for removing permission
- '=' is usded for setting permission

For example, if you want to set the permission such that the user can read, write, and execute it and memebers of your group can read and execute it, and others may only read it.

Then the command for this will be:
```
$ chmod u=rwx,g=rx,o=r <filename>
```
### Absolute mode
  
  The general syntax to change permission using Absolute mode is as follows:
  
 ```
$ chmod <permission> <filename>
``` 
  The Absolute mode follows octal representation.
  
  The leftmost digit is for the user, the middle digit is for the user group and the right most digit is for all.
  
| 0 | No permission |---|
| - | :------------- |---|
| 1 | Execute permission | --x|
| 2 | Write Permission | -w-|
| 3 | Execute and Write | -wx|
| 4 | Read Permission | r--|
| 5 | Read and Execute | r-x|
| 6 | Read and Write | rw-|
| 7 | Read, Write and Execute | rwx|
  
For example, if you want to set the permission such that the user can read, write and execute it and members of your group can read and execute it and others may only read it.
  
Then the command for this will be:
  ```
$ chmod 754 <filename>
``` 
