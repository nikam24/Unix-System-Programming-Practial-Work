# Automating a Shell Script using Crontab

In this project, we demonstrate how to automate a shell script using crontab on a Linux-based operating system. This guide assumes that you already have a shell script that you want to automate, and a basic understanding of the command line and crontab.

Our shell script will write into mylog.txt file every minute.
Shell script : 
![Screenshot description](https://github.com/nikam24/Unix-System-Programming-Practial-Work/blob/main/Screenshot%20from%202023-02-11%2016-30-08.png)

## Prerequisites
- Linux-based operating system (such as Ubuntu)
- Text editor (such as nano or vim)
- Terminal access
- Shell script to automate

## Steps
1. Open terminal and run the command `crontab -e`. This will open the crontab editor.
```
crontab -e
```
[Screenshot description](https://github.com/nikam24/Unix-System-Programming-Practial-Work/blob/main/Screenshot%20from%202023-02-11%2016-34-43.png)
2. In the editor, add the following line at the end: `* * * * * /path/to/script.sh`. This sets the cronjob to run the script every minute.
```
* * * * * /path/to/script.sh
```
[Screenshot description](https://github.com/nikam24/Unix-System-Programming-Practial-Work/blob/main/Screenshot%20from%202023-02-11%2016-34-51.png)
3. Save and close the editor. 
4. Check if the cronjob was correctly set by running `crontab -l`.
```
crontab -l
```
[Screenshot description](https://github.com/nikam24/Unix-System-Programming-Practial-Work/blob/main/Screenshot%20from%202023-02-11%2016-35-06.png)
5. Wait for a minute and check the output of the shell script in the log file.

Before updating log file : 
[Screenshot description](https://github.com/nikam24/Unix-System-Programming-Practial-Work/blob/main/Screenshot%20from%202023-02-11%2016-30-35.png)

After updating log file :
[Screenshot description](https://github.com/nikam24/Unix-System-Programming-Practial-Work/blob/main/Screenshot%20from%202023-02-11%2016-30-44.png)

Note: 
- The path to the script must be the absolute path, not the relative path.
- In the above line, the five stars (`* * * * *`) represent the schedule of the cronjob, where the first field is for minutes (0-59), the second for hours (0-23), the third for days of the month (1-31), the fourth for months (1-12), and the fifth for days of the week (0-7, both 0 and 7 represent Sunday). You can modify this to run the script at a specific schedule.
- If your script requires environment variables, you need to set them in the crontab file.

## Conclusion
In this project, we learned how to automate a shell script using crontab on a Linux-based operating system. We hope this guide will help you automate your own shell script.
