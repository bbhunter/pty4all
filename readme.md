# pty4all

Hey mate, are you:

- Tired of shitty reverse shell?
- Tired of hittinc ^C and loosing your shell?
- Tired of overcomplicated C2?
- In need of a real pty with auto completion and signals?
- In need of a minimalistic payload that spawns a shell?
- In need of easy-peasy persistancy?

Say no more, `pty4all` got you all covered!

By using its cutting edge technology (lolnope), you can now have a persistent multi reverse pty handler!

![This is an image](meme.png)


# Usage

```bash
./socat-multi-handler.sh
# Usage : ./socat-multi-handler.sh --lhost <LHOST> --lport <LPORT> --webport <WEBPORT> [--dnotify <WEBHOOK> ] [--persist]
# Demo 1: ./socat-multi-handler.sh --lhost X.X.X.X --lport 443 --webport 80
# Demo 2: ./socat-multi-handler.sh --lhost X.X.X.X --lport 443 --webport 80 --dnotify https://discord.com/api/webhooks/XXXX/YYYY --persist

# Update your shell size: paste the result of this command in your rev-shell
echo "stty rows $LINES cols $COLUMNS"
# Make your shell smooth, fix ^L etc
export TERM=xterm-256color
```


# Demo

https://www.youtube.com/watch?v=TTEGIhvu7eQ
[![demo pty4all](demo.png)](https://www.youtube.com/watch?v=TTEGIhvu7eQ)


# Features

- Fully interactive pty (socat)
- Persistent handler on host (tmux)
- Fully encrypted (self signed https)
- Minimalistic payload (python, curl)
- Persistency on victim (pgrep, crontab)
- Stealth-ish (crontab trick & space before commands to prevent history)
- Push notification (Discord webhook)


# Requirements

- Target must be x64 unix-based with curl installed, but a few tweaks can "make things work", I've had success for ARM & MIPS.
- Host must have socat, tmux, python, openssl, and curl installed: `sudo apt update && sudo apt install -y socat tmux curl python openssl`

# Kudos

- https://systemoverlord.com/2018/01/20/socat-as-a-handler-for-multiple-reverse-shells.html
