# Multi-Process PipeServer

![Project Status](https://img.shields.io/badge/status-unmaintained-red.svg)

This is a Multi-Process PipeServer project that I created when I was bored. It allows you to spawn multiple pipes based on the number of configurations available in the `_configs` list. The first pipe (`pipe0`) is reserved as the main communication pipe for any frontend application or bot.

The project uses `StreamReader` and `StreamWriter` to enable different child processes to communicate, leveraging the WIN32 API. The `pipe0_bridge_win32api.py` file is a demo client that connects to the `pipe0` pipe and sends commands to the PipeServer.

The PipeServer then passes the arguments and starts a worker that will run a scheduled job until it exits. The worker will authenticate to Telegram services and, based on the run mode, it can either dump information from groups, store it in a CSV file, or use the CSV to send messages to groups or channels (which is currently not implemented).

## Features

- Spawn multiple pipes based on the number of configurations available
- Communicate between child processes using `StreamReader` and `StreamWriter`
- Authenticate to Telegram services and perform various actions (dump information, send messages)
- Utilize a CSV file to store and retrieve group/channel information

## Getting Started

To use this project, you'll need to have the necessary dependencies installed, such as the `WTelegramClient` library. You can install it using the following command:

``` command:

dotnet add package WTelegramClient --version 4.1.8


## Contributing

This project is currently unmaintained, as I created it when I was bored. If you find it interesting and would like to contribute, feel free to fork the repository and submit pull requests.

