title: Job Sheduler

For receiving data from sensors every day at the exact time you need to use [Cron](https://en.wikipedia.org/wiki/Cron) to shedule jobs.



Setup cron job that sends a request at 6:00, 15:00, 18:00 (London time) every day:

```bash
gcloud sheduler jobs create http fucntion_name \
  --location=path_to_function                  \
  --shedule="0 6,15,18 1-31 1-12 0-7"          \
  --uri=""                                     \
  --http-method=GET                            \
  --time-zone=zone_name                       
```
