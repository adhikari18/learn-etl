# Unix
Mastering the ETL Process with Essential UNIX Commands: A Tutorial

## Introduction:
UNIX commands have long been the backbone of data processing and manipulation in the ETL (Extract, Transform, Load) process. Whether you are working with large datasets or performing routine data tasks, understanding these commands can significantly enhance your efficiency and effectiveness. In this tutorial, we will explore several essential UNIX commands that are invaluable for data engineers and analysts involved in ETL processes.

## Commands
### Navigating File System
#### pwd - Print the current working directory
```bash
pwd
```

#### ls - List files and directories
```bash
ls
ls -l    # Detailed list
ls -a    # Show hidden files
```

#### cd - change directory
```bash
cd /path/to/directory
cd ..    # Move up one directory
```

### File Manipulation
#### cp - copy files or directories
```bash
cp file.txt /destination
```

#### mv - Move or rename files:
```bash
mv file.txt newfile.txt
mv file.txt /new/location
```

#### rm - Remove files or directories:
```bash
rm file.txt
rm -r directory/    # Remove directory and its contents
```

### File Viewing and Text Manipulation

#### cat - Display file content:
```bash
cat file.txt
```
#### less - Display file content page by page:
```bash
less file.txt
```
#### grep - Search for a specific string in files:
```bash
grep "pattern" file.txt
```
### Data Transformation
#### cut - Extract specific columns from a file:
```bash
cut -d',' -f2,4 file.csv    # Extract columns 2 and 4 (comma-separated)
```
#### awk - Powerful text processing tool:
```bash
awk '{print $2}' file.txt    # Print second column
```
#### sed - Stream editor for text manipulation:
```bash
sed 's/old/new/g' file.txt   # Replace 'old' with 'new'
```
### Data Filtering
#### sort - Sort lines in a file:
```bash
sort file.txt
```
#### uniq - Filter out duplicate lines:
```bash
uniq file.txt
```
#### head and tail - Display the first or last few lines of a file:
```bash
head -n 10 file.txt    # Display first 10 lines
tail -n 20 file.txt    # Display last 20 lines
```
### File Compression and Decompression
#### gzip - Compress files:
```bash
gzip file.txt    # Creates file.txt.gz
```
#### gunzip - Decompress files:
```bash
gunzip file.txt.gz
```
### Running Scripts and Executables
#### chmod - Change file permissions:
```bash
chmod +x script.sh    # Add execute permission
```
#### ./ - Run a script or executable:
```bash
./script.sh
```

### Redirection and Pipes
#### > - Redirect output to a file (overwrite):
```bash
echo "Hello, World!" > output.txt
```
#### >> - Redirect output to a file (append):
```bash
echo "More text" >> output.txt
```
#### | - Pipe operator to pass output from one command as input to another:
```bash
cat file.txt | grep "pattern"
```

### Variables and Environment
#### export - Set environment variables:
```bash
export MY_VARIABLE=value
```
#### $VARIABLE - Access the value of an environment variable:
```bash
echo $PATH
```
### Loops and Control Structures
####  for loop - Iterate over a list of items:
```bash
for item in item1 item2 item3; do
   echo $item
done
```
#### if statement - Conditional execution:
```bash
if [ condition ]; then
   echo "Condition is true"
fi
```
### Remote File Operations (SSH)

#### scp - Securely copy files between local and remote systems:
```bash
scp local_file.txt user@remote_host:/path/to/destination
```
#### ssh - Securely connect to a remote system:
```bash
ssh user@remote_host
```
### Finding and Managing Processes
#### ps - Display currently running processes:
```bash
ps aux
```
#### kill - Terminate a process by its process ID:
```bash
kill PID
```
### Cron Jobs for Scheduled Tasks
#### crontab - Edit user-specific cron jobs:
```bash
crontab -e

# Example of a crontab entry to run a script every day at 2:00 AM:

0 2 * * * /path/to/script.sh
```
### Monitoring Disk Usage
#### df - Display disk space usage:
```bash
df -h
```
#### du - Display file and directory disk usage:
```bash
du -sh /path/to/directory
```

## Cheat sheet
[Unix command cheat sheet](https://www.alexji.com/UNIXCheatSheet.pdf)
