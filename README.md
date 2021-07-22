# sshbot

## What is sshbot?
### Introduction
sshbot is a simple Discord bot designed for allowing users to run and execute commands on a remote machine using the SSH2 library for NodeJS. This can be used for anything from an Amazon EC2 instnce all the way to a Raspberry Pi.

![example](https://i.imgur.com/BGLBRWZ.png "example")

### Uses and Limitations
While the bot is mostly for fun, it can be used for just about anything that can be done on a remote machine through SSH. This includes running and compiling code, installing software and having entire conversations through cowsay. Unfortunately since Discord is a limited interface, the bot cannot print responses over 2000 characters or display the output from programs that don't immediately terminate such as Vim.

## Running sshbot
### Getting Everything Ready
The first step for running this bot is to clone the Git repository and download all the bots dependencies through NPM. This can be done through a shell terminal with the following commands.
```sh
git clone https://github.com/dominictoms/sshbot.git
cd sshbot
npm install
```

### Enviroment Variables
For security reasons, all the secrets needed to run the bot are stored as enviroment variables in a file called `.env`. To add all your enviroment variables, simply create the file and use a text editor to add your values. The file should look like the following example.
```sh
DISCORD_KEY = abcdefghijk...
SSH_HOST = 127.0.0.1
SSH_PORT = 22
SSH_USER = dominictoms
SSH_KEY = ./sshkey.pem
```

### Configuring the Bot
You can configure the bot to meet your specific needs through the `config.json` file. The config file should look like the example below.
```json
{
    "prefix": "$",
    "roles": ["admin", "mod"]
}
```
Please note that if you want anyone in the server to have access to the bot, the `roles` array should contain `"@everyone"` as an element.

### Running the Bot
Now that everything has been set up it's time to actually run the bot. The bot can be run locally with the following command.
```sh
node .
```

### Using the Bot
Once the bot is up and running in your server, usage is incredibly simple. Simply type the prefix you specified in the config file followed by the command you want to run on your remote machine. If you want to output the contents of the help file, simply send a message containing your prefix followed by `help`.
