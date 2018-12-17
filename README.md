# YouView_Coding_Exercise
Python Coding Exercise from YouView -- The "cron" test

A pretty simple problem. We think this task should easily take you less than 2-3 hours.

We have a set of tasks, each running at least daily, which are scheduled with a simplified cron. We want to find when each of them will next run.

The scheduler config looks like this:
```
30 15 /bin/run_me_daily
45 * /bin/run_me_hourly
* * /bin/run_me_every_minute
* 19 /bin/run_me_sixty_times
```
The first field is the minutes past the hour, the second field is the hour of the day and the third is the command to run. For both cases * means that it should run for all values of that field. In the above example run_me_daily has been set to run at 3I30pm every day and run_me_hourly at 45 minutes past the hour every hour. The fields are whitespace separated and each entry is on a separate line.

We want you to write a command line program that when fed this config to stdin, and the current time in the format HH:MM as a command line argument, outputs the soonest time at which each of the commands will fire and whether it is today or tomorrow. When it should fire at the current time that is the time you should output, not the next one.

So - just to be clear - the following should work as a means of running your solution:
solution 10:00 < crontab

Where solution corresponds to your executable/script.

Given the above examples as input and the command-line argument 16:10 the output should be
```
       15:30 tomorrow - /bin/run_me_daily
       16:45 today - /bin/run_me_hourly
       16:10 today - /bin/run_me_every_minute
       19:00 today - /bin/run_me_sixty_times
```
