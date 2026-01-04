# hyprland-greetd-tuigreet
minimalistic login screen

Minimalist Login Manager: greetd + tuigreet
This repository contains the configuration for a highly minimalist, industrial-style login manager setup using greetd and the tuigreet greeter. As featured in The Most Minimalist Login Manager for Hyprland, this setup is perfect for tiling window managers like Hyprland.

🚀 Overview
greetd: A flexible login manager daemon that doesn't make assumptions about what you want to run.

tuigreet: A TUI (Terminal User Interface) greeter for greetd. It is lightweight, simple, and provides a "Half-Life" or industrial aesthetic [01:45].

✨ Features
Session Management: Easily switch between Hyprland, GNOME, or other window managers using F2 or F3 [02:10].

Custom Greetings: Personalize your login screen (e.g., "Authorized Personnel Only") [02:04].

Remember Username: Automatically saves the last used username for quicker logins [05:40].

Password Masking: Feedback via asterisks while typing your password [05:47].

Power Actions: Built-in support for shutdown and reboot directly from the TUI [03:03].

🛠 Installation & Setup
Install the packages: Install greetd and greetd-tuigreet using your distribution's package manager.

Create the configuration directory: If the folder doesn't exist, create it and the config file:

Bash

sudo mkdir -p /etc/greetd && sudo touch /etc/greetd/config.toml
``` [[04:14](http://www.youtube.com/watch?v=c2b6-HJNkc0&t=254)]

Apply Configuration: Copy the configuration provided below into /etc/greetd/config.toml.

Enable the Service:

Bash

sudo systemctl enable --now greetd
🎨 Theming
tuigreet supports basic terminal colors. Note that "Yellow" often appears as an orange/brown hue, while "Bright Yellow" appears as true yellow [07:07]. You can customize the border, text, and prompt colors within the command flags.

📄 Default config.toml
Based on the video, here is the recommended configuration for /etc/greetd/config.toml. This setup ensures tuigreet launches on boot and remembers your session.

Ini, TOML

[default_session]
# The command to start tuigreet
# --remember: remembers the last username [00:05:40]
# --asterisks: shows * for password characters [00:05:47]
# --greeting: your custom text [00:06:03]
# --cmd: the command to run after login (e.g., Hyprland) [00:02:20]
command = "tuigreet --remember --asterisks --greeting 'Authorized Personnel Only' --window-search --time --cmd Hyprland"

# The user to run the greeter as
user = "greeter"

[terminal]
# The VT to run the greeter on
vt = 1
Key Flags Explained:
--remember: Remembers the last successful username [08:17].

--asterisks: Provides visual feedback for password entry [05:55].

--greeting 'Text': Sets the custom header message [06:10].

--cmd Hyprland: Sets the default environment to launch [02:20].

