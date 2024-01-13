


## Overview
An advanced real-time CLI chat application designed to eliminate language barriers, connecting individuals globally. It facilitates collaboration by seamlessly translating messages using the OpenNMT ArgoTranslate machine-learning model and the `Ably Realtime Framework` for smooth communication.

### Supported Languages
Supports diverse languages, including English, Hindi, French, German, Italian, Polish, Spanish, Russian, Japanese, and Chinese.

## Prerequisites
Ensure the following prerequisites are installed before use:
- [ABLY_KEY](https://ably.com/)
- [Go](https://golang.org/)
- [Docker](https://www.docker.com/get-started)

## Setup
Follow these steps to set up the project:

1. Run LibreTranslate Docker container to load supported languages:
   ```
   docker run -it -p 5000:5000 libretranslate/libretranslate --load-only en,hi,fr,de,it,pl,es,ru,ja,zh
   ```

2. Clone the repository:
   ```
   git clone https://github.com/yrs147/cling-ably.git
   cd cling-ably
   ```

3. Obtain your `ABLY_KEY` and add it to the `.env` file.

4. Add dependencies:
   ```
   go mod tidy
   ```

5. Build the binary:
   ```
   go build -o chatapp
   ```

6. Run the application:
   ```
   ./chatapp -u <username> -r <roomname> -l <preferredlanguage>
   ```

## Command and Flags
Provides the following commands and flags:
```
Usage: chatapp [flags]

A CLI chat app using Ably

Flags:
  -h, --help          Help for chatapp
  -u, --username      Your username for the chat (default "defaultUsername")
  -r, --room          Chat room code (default "defaultRoomCode")
  -l, --language      Chat room language code (default "en")
```
- `username (-u)`: Set your chat username (default is "defaultUsername").
- `room (-r)`: Set the chat room code (default is "defaultRoomCode").
- `language (-l)`: Set the chat room language code (default is "en").