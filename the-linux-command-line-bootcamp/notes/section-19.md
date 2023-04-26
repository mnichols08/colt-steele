# Cron

The `cron` service allow sus to schedule commands to run at regular intervals like: 
- Every 30 minutes
- Every day at midnight
- Every 1st of the month
- Every December 15th

Editing the crontab
To set up a cron job, we need to edit the crontab configuration file. Rather than edit the files directly, it is best to use the `crontab - e` command.

Cron Syntax
a | b | c | d | e | command
-|-|-|-|-|-
minute (0-59) | hour (0-23) | day (1-31) | month (1-12) | Day of Week (0-6) | 