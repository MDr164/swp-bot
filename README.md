# swp-bot

This is a Discord Bot which can interact with the REST API of Bitbucket and soon Jira.
It was created as a tool to aid team dynamic in a software project, hence the name swp-bot.
In order to work correctly, the resulting binary needs to be invoked with a config file
via `-config` which for now is written in json and should be filled as follows:

```
{
"BITBUCKET_TOKEN": "<TOKEN>",
"DISCORD_TOKEN": "<TOKEN>",
"BITBUCKET_URL_1": "https://your.bitbucket.instance/rest/api/1.0/path/to/your/repo/pull-requests?limit=5",
"PING_CHANNEL": "<DISCORD_CHANNEL_ID>",
"RELAY_CHANNEL": "<DISCORD_CHANNEL_ID>",
"<BITBUCKET_USERNAME>": "<DISCORD_USER_ID>",
"<DISCORD_USER_ID>": "<BITBUCKET_USERNAME>",
"VIP": "<DISCORD_USER_ID>"
}
```

The number of users in this file is not restricted, each user should be written down
with both the Bitbucket username first and second for now. The VIP is restricted to one
for now, but can be extended to an unlimited amount soon. The `Limit=5` is added
to the URL simply to comply with Discords 6000 character limit. In addition to the config,
a port to listen for webhook events can be specified via `-port` and defaults to 50015.
