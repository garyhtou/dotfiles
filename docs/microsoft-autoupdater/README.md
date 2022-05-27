Microsoft AutoUpdater keeps popping up. It's annoying!

> https://superuser.com/questions/1544338/turn-off-microsoft-apps-microsoft-autoupdate-app-on-a-mac

Extend auto update checking interval:

```sh
# check current config content
plutil -p /Library/LaunchAgents/com.microsoft.update.agent.plist

# backup
cp -a /Library/LaunchAgents/com.microsoft.update.agent.plist .

# check every 604,800 seconds (7 days). Default is 2 hours i think
sudo plutil -replace StartInterval -integer 604800 /Library/LaunchAgents/com.microsoft.update.agent.plist
```

The backup file (`com.microsoft.update.agent.plist`) is located in the same directory as this README.

