# TonStation Automation Script

This script automates various interactions with the TonStation API, including tasks such as authentication, farming, and quest handling for multiple user accounts. The script uses JavaScript with `axios` for HTTP requests, `luxon` for date and time manipulation, and `colors` for enhanced console output.

## Features

- **User Authentication**: Logs into TonStation for each user account.
- **Farm Management**: Checks and starts farming activities and claims rewards when available.
- **Quest Handling**: Retrieves available quests, starts them, and claims rewards when completed.

## Requirements

- Node.js (v14 or higher)
- NPM packages:
  - `axios`
  - `colors`
  - `luxon`
  - `readline`

## Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd <repository-name>
   ```

2. Install the required dependencies:
   ```bash
   npm install
   ```

3. Create a `data.txt` file in the root directory. Each line should contain the `initData` required for user authentication.

## Usage

Run the script using Node.js:

```bash
node script.js
```

The script will:
- Authenticate each user listed in `data.txt`.
- Manage farming tasks by checking if current farming activities are complete and initiating new ones if necessary.
- Retrieve quests for each user, starting and claiming rewards when applicable.

## Configuration

You may need to adjust the `skipTaskIds` array within the `TonStation` class to include specific quest IDs that you want the script to ignore.

### Important Notes

- **Error Handling**: If an error occurs, it is important to retrieve the `Query_id` before re-running the script. This will ensure the script can continue executing without issues.
- **Countdown Timer**: After completing all actions for each user, the script enters a countdown period of 8 hours (`480 * 60` seconds) before restarting the loop.

## Logging

The script uses various log types with color-coded output:
- **Success** (`green`): Indicates successful actions (e.g., logging in, claiming rewards).
- **Warning** (`yellow`): Warns about tasks that are skipped.
- **Error** (`red`): Shows when an error has occurred.
- **Info** (`blue`): General information about the current status of actions.

## Dependencies

This project uses the following dependencies:
- `axios` - for making HTTP requests.
- `luxon` - for date and time operations.
- `colors` - for colorized console logs.
- `readline` - for managing countdown displays in the console.

## License

This project is open-source and available under the MIT License.
