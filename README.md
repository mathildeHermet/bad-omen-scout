# bad-omen-scout

Track bugs commits or relases on opensource projects beeing notify on chats channels or other tools.

## Build

Build is basic right now. Just build it by cloning github repository then build it with go CLI on the machine where it is supposed to be run.

```bash
git git@github.com:mathildeHermet/bad-omen-scout.git
cd bad-omen-scout
go build -o bad-omen-scout main.go
```

## Daemon creation example

```bash
[Unit]
Description=bas-ormen-scout warning for github projects released notifyiing a configured chats.
After=network.target

[Service]
ExecStart=/usr/local/bin/bad-omen-scout --github-repo https://github.com/orga/repo --refresh-interval 10m --cache-file /var/lib/bad-omen-scout/repo.txt --discord-hook-url "https://my-chat/webhook-to-channel"
WorkingDirectory=/usr/local/bin # Adapt location depending on binaries installation folder
User=root
Group=root

[Install]
WantedBy=multi-user.target
```
