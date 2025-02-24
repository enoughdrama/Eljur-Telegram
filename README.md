# Eljur Timetable Parser

Eljur Timetable Parser is a C# application designed to parse, monitor, and notify users about timetable changes from the Eljur web service. Integrated with a Telegram Bot, the project notifies users in real-time about updates, such as new homework assignments or grade changes. The project also incorporates data caching and simple encryption to securely store user credentials.

---

## Table of Contents

- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)

---

## Features

- **Timetable Parsing:** Extracts daily and weekly schedules from the Eljur website.
- **Real-Time Updates:** Automatically checks for updates at regular intervals.
- **Telegram Bot Integration:** Sends notifications to users about timetable changes.
- **Data Caching:** Utilizes local caching to detect changes and avoid redundant notifications.
- **Encryption:** Implements AES encryption for storing sensitive user credentials securely.
- **User Authentication:** Supports user authentication via Telegram commands.

---

## Requirements

- **.NET 5.0 or later** – Ensure you have a compatible version of the .NET runtime.
- **Telegram Bot Token** – A valid Telegram bot token is required to enable bot functionalities.
- **NuGet Packages:**
  - [AngleSharp](https://www.nuget.org/packages/AngleSharp/)
  - [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/)
  - [Telegram.Bot](https://www.nuget.org/packages/Telegram.Bot/)

---

## Installation

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/enoughdrama/Eljur-Telegram.git
   cd Eljur-Telegram
   ```

2. **Restore Dependencies:**

   Use the .NET CLI to restore necessary packages:

   ```bash
   dotnet restore
   ```

3. **Build the Project:**

   Compile the application using:

   ```bash
   dotnet build
   ```

---

## Configuration

1. **Telegram Bot Token:**

   Open the `Program.cs` file and insert your Telegram bot token into the `TelegramToken` constant:

   ```csharp
   private static readonly string TelegramToken = "YOUR_TELEGRAM_BOT_TOKEN_HERE";
   ```

2. **Directory Structure:**

   The application automatically creates the required directories (`db` and `db/cache`) for storing user data and cache files.

---

## Usage

1. **Starting the Application:**

   Run the application from the command line:

   ```bash
   dotnet run
   ```

2. **Bot Commands:**

   - **/start:** Initiates the bot and displays available options.
   - **/auth `<username>` `<password>`:** Authenticates and registers a user. Credentials are encrypted and stored locally.
   - **📅 Расписание на сегодня:** Displays today’s schedule.
   - **📅 Расписание на завтра:** Displays tomorrow’s schedule.
   - **📅 Текущая неделя:** Displays the full weekly schedule.

3. **Timetable Updates:**

   The application automatically checks for timetable changes at regular intervals (approximately every 86 seconds). When changes are detected, the bot notifies the user with details about updated homework and new grades.

---

## Project Structure

```
Eljur-Telegram/
├── db/                # Directory for user data and cache files
│   └── cache/         # Directory for cached timetable data
├── Program.cs         # Main program file containing core functionality
├── README.md          # Project documentation
└── ...                # Other necessary files and directories
```

- **Program.cs:** Contains the logic for:
  - Telegram Bot command handling
  - User authentication
  - Parsing HTML from the Eljur website using AngleSharp
  - Encryption and decryption of user data
  - Scheduling periodic checks for timetable updates

---

## Contributing

Contributions are welcome! Please follow these steps to contribute:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Write clear and concise commit messages.
4. Submit a pull request detailing your changes.

For any issues or suggestions, please open an issue in the repository.

---

## License

This project is licensed under the [MIT License](LICENSE). Feel free to use, modify, and distribute the software according to the license terms.

---

Eljur Timetable Parser offers a robust solution for monitoring timetable changes and automating user notifications via Telegram. Its modular design and clear structure make it easy to extend and customize for additional functionalities or integration with other systems.

Enjoy using Eljur Timetable Parser!
