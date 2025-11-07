# 🔄 Input, Output, and Piping in Linux

---

## 🧩 Standard Streams

Every process in Linux works with three main streams:
- **stdin (0)** — Standard Input  
- **stdout (1)** — Standard Output  
- **stderr (2)** — Standard Error  

Programs read data from `stdin` and print results to `stdout`. Errors go to `stderr`.

Example:
```bash
ls /home > output.txt  # Redirect output to file
ls /wrong 2> error.txt  # Redirect errors to another file

File Descriptors

Each stream has an identifier:

0 → stdin

1 → stdout

2 → stderr

You can use these numbers for precise control, e.g.:
command 1> out.txt 2> err.txt
---
Pipes (|)

The pipe operator connects commands by sending the output of one command as input to another.

Example:
ls -la /etc | less

This sends the list of files to less for easier reading.

You can also chain commands:
ls /bin | grep "bash"
---
The tee Command

tee duplicates output — showing it on screen and writing it to a file.

Example:
ls | tee list.txt
ls /etc | tee etc_list.txt | grep "conf"
---
The env Command

env shows all environment variables currently active in the system.

Example:
env
Use it to inspect paths, user variables, and program configurations.
