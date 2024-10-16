# Backups all cron jobs

To add some more cool commands for backuping and restoring crontab. Might be useful.

# Backup periodically current cron with cron :)

0 9 * * * crontab -l | gzip > /backups/'crontab-'$(date +"\%Y\%m\%d-\%H\%M\%S")'.gz'
Restore Single User Cronjobs from Backup. Below is two commands which will restored jobs from backup created in above step.

crontab cron-backup.txt
crontab -u john john-cron-backup.txt

# Backup all users crontabs

zip -r cronjobs-all.zip /var/spool/cron
