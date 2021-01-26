# linux-storage-notifier
Will email if the storage is near full

## Requirements
• check if HOSTNAME is properly set
  - To check or change the hostname `sudo nano /etc/sysconfig/network`
  
• install mail `yum install mailx -y`

## Procedure
1. SSH to the server
2. Change directory to /opt/scripts

    If /opt/scripts does not exist then make the directory
    
3. Copy the file (storage-notifier.sh) above and paste it to the /opt/scripts 
or at the /opt/scripts directory type: `sudo nano storage-notifier.sh` then copy and paste the code above.
4. Make it executable, in the same directory run `sudo chmod +x storage-notifier.sh`
5. Try to run if it’s working
6. Add to cronjob
7. Type `sudo crontab -e` then insert the code below
  `0 0 * * 0 /bin/bash /opt/script/storage-notifier.sh`
  this will run every sunday, you can change it if you want
 
DEFAULT VALUE:
max 80% 
- meaning will only email if the storage is 80% used.
- you can change it in the code find the 80 then change it `if [ $used -ge 80 ]; then`
