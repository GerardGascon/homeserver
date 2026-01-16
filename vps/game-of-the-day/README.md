# Game of the Day trigger

Used to trigger the update of Game of the Day's website

> [!NOTE]
> This might eventually become a docker container, but for now it is a shell script.

## Requirements

You need to install GitHub CLI on the host machine

Create a file containing an api token for triggering GitHub Actions.

## Cron job

```
0 0 * * * <<path to game of the day trigger>>/trigger-workflow.sh
```