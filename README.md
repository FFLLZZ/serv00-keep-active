# serv00-keep-active

Keep ser00 active, SSH the server every 3 days.
It's only use github action, not use any other code (Python, JavaScript, ...)

## How to use   [中文说明](./README-cn.md)  
### Prepare  
if you have ssh key pair ( public key file have copyed to the server ) and telegram TOKEN/chat_id, you need not do the step.  
1. generate SSH key pair  
    - use command `ssh-keygen -t rsa -b 4096` to generate RSA key pair. Your key files will be saved in `/home/your_user/.ssh/`, `id_rsa` is private key, `id_rsa_pub` is public key.  
    - use `cat ~/.ssh/id_rsa` and copy the message to your repo secret `SSH_PRIVATE_KEY`.      - 使用 'cat ~/.ssh/id_rsa' 并将消息复制到您的存储库密钥 'SSH_PRIVATE_KEY'。      - 使用 'cat ~/.ssh/id_rsa' 并将消息复制到您的存储库密钥 'SSH_PRIVATE_KEY'。     - 使用 'cat ~/.ssh/id_rsa' 并将消息复制到您的存储库密钥 'SSH_PRIVATE_KEY'。  
    - use `ssh-copy-id username@server_ip` copy the public key file message to your serv00 server.  
2. generate telegram bot, get token and chat_id  
    - find `@BotFather` in Telegram, creat a new bot and get `BOT_TOKEN`      - 在 Telegram 中找到“@BotFather”，创建一个新机器人并获得“BOT_TOKEN”  
    - use `https://api.telegram.org/bot<YourBotToken>/getUpdates` send messge to BOT, you can find `chat_id` in respones JSON (if get NULL JSON, you should send message to the Bot in telegram first and try get chat_id again.)        - 使用 'https://api.telegram.org/bot/getUpdates' 发送消息给 BOT，你可以在 respones JSON 中找到 'chat_id' （如果得到 NULL JSON，你应该先在 Telegram 中向 Bot 发送消息，然后再次尝试 get chat_id。        - 使用 'https://api.telegram.org/bot/getUpdates' 发送消息给 BOT，你可以在 respones JSON 中找到 'chat_id' （如果得到 NULL JSON，你应该先在 Telegram 中向 Bot 发送消息，然后再次尝试 get chat_id。       - 使用 'https://api.telegram.org/bot/getUpdates' 发送消息给 BOT，你可以在 respones JSON 中找到 'chat_id' （如果得到 NULL JSON，你应该先在 Telegram 中向 Bot 发送消息，然后再次尝试 get chat_id。    

生成：ssh-keygen -t rsa -b 4096
查看：ls -l .ssh查看：ls -l .ssh
复制：cat ~/.ssh/id_rsa


### Steps
1. Fork the repo  
2. your repo `Settings` -> `Secrets and variables` -> `Actions`, `New repository secret`, add secrets:

| secret | value |
|-------|-------|
| SERVER_IP | your serv00 IP |
| USERNAME | your serv00 ssh usename |
| SSH_PRIVATE_KEY | your private key |
| TELEGRAM_BOT_TOKEN | your telegram bot token |
| TELEGRAM_CHAT_ID | your telegram chat id |  
