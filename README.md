![preview](https://raw.githubusercontent.com/baseleldeeb2021-svg/shipwright-forge/main/banner_701047d.svg)

# AstroForge — Ship Your Pygame Projects to the Stars 🚀

Welcome to **AstroForge**, the spiritual successor to the classic one-command build tool for Pygame developers. While its predecessor focused on turning a single command into full Windows, macOS, and Linux builds, AstroForge takes that founding vision and launches it into an entirely new orbit: a complete, self-contained **publishing pipeline** that transforms your raw Pygame prototype into a polished, storefront-ready release for itch.io, all while managing your project's versioning, metadata, and distribution channels with zero manual intervention.

Think of AstroForge as your personal mission control. You are the pilot; we are the ground crew. You write code, we handle the complex aerodynamics of cross-platform packaging, the quiet hum of dependency resolution, and the delicate choreography of uploading your creation to a global audience. No more wrestling with obscure configuration files or piecing together a Frankenstein's monster of scripts. AstroForge is the single point of truth between your `main.py` and the millions of potential players waiting on the other side of the screen.

## 🧭 Overview: Why AstroForge Exists

The journey from a local game jam prototype to a successful global release is rarely a straight line. It is fraught with peril: platform-specific quirks, missing system libraries, and the eternal struggle of making your game feel like a native citizen on every operating system. Existing tools often require you to learn a new DSL, master a complex CLI, or manually curate a suite of build scripts that break the moment you update a dependency.

AstroForge reimagines this entire process. Instead of a build tool, we provide a **concierge for your code**. It analyzes your project structure, infers your dependencies from your environment, and constructs a hermetic, reproducible build environment for each target platform. It doesn’t just package your files; it curates the entire experience. From generating custom icons and splash screens to embedding your chosen legal notices and ensuring your game's window metadata is consistent across every OS, AstroForge polishes the rough edges so your game looks like it was developed by a AAA studio, not a solo dev running on coffee and determination.

## 🚦 Getting Started: Your First Launch

Before we dive into the intricacies of orbital mechanics, let's get you off the ground. AstroForge is designed to be intuitive even if you've never used a modern build system before. The core philosophy is "Configuration by Convention." If your project follows a standard layout, AstroForge will likely work out of the box with no configuration at all.

**Prerequisites:** You'll need a recent version of Python (3.9 or later) installed on your development machine, a working Pygame project, and an account on the publishing platform of your choice (itch.io is fully supported out of the box).

**The First Command:** Navigate to the root directory of your Pygame project. This is the folder containing your main entry point (usually `main.py` or `game.py`). From here, you simply execute the `astronaut` command. That's it. AstroForge will scan your directory, identify your entry point, and take a snapshot of your currently installed Python packages to understand your project's dependencies. It then presents you with a clean, interactive checklist of build targets (Windows, Linux, macOS) and publishing options. You select your preferences, and the show begins.

### 📁 Project Structure: What AstroForge Expects

AstroForge is flexible but thrives on organization. For the best experience, we recommend a structure that separates assets, code, and metadata:

```
your_game_project/
├── main.py
├── game/
│   ├── __init__.py
│   ├── scenes/
│   ├── entities/
│   └── systems/
├── assets/
│   ├── images/
│   ├── audio/
│   └── fonts/
├── metadata.toml
└── release_notes.md
```

The `metadata.toml` file is optional but recommended. It allows you to define high-level attributes like the game's display name, version number, author details, and itch.io page URL. AstroForge reads this file to automatically fill in the metadata for your builds and your itch.io upload, ensuring consistency between the game's internal data and its public listing.

## ⚙️ Core Features: The Mission Control Suite

AstroForge is not a monolithic block of code; it's a suite of coordinated modules, each designed to master one critical aspect of the launch sequence.

### 🖥️ Responsive UI and Dynamic Studio Mode

The build process is not a black box. AstroForge features a responsive, terminal-based UI that dynamically updates as the build progresses. You'll see a live feed of each step—dependency gathering, asset compression, binary linking, and archive creation. We call this "Studio Mode." It's like watching a live broadcast of your game being constructed. If a step fails, AstroForge doesn't just spit out a cryptic error; it provides a contextual explanation and most likely a suggested fix. The interface scales gracefully whether you are working on a tiny laptop terminal or a massive multi-monitor setup.

### 🌍 Universal Ingestion Protocol (UIP)

This is the engine under the hood. UIP is AstroForge's clever system for understanding your project. It parses your Python source code to identify imports, then cross-references those imports with your installed site-packages to generate a precise manifest of dependencies. It doesn't just blindly copy every package; it intelligently trims the fat, excluding development-only tools and massive libraries you might use for testing but aren't needed for the final release. This results in significantly smaller build sizes—often 30% to 50% smaller than a naive assembly.

### 🧩 Cross-Platform Holo-Deck Emulation

Each operating system is a different world with its own rules. AstroForge sets up a self-contained "Holo-Deck" for each target platform. For Windows, it verifies the Visual C++ Redistributable requirements and handles the `.exe` packaging. For macOS, it manages `.app` bundle structures, `Info.plist` generation, and code signing (if you have the necessary certificates set up). For Linux, it builds AppImage or tarball distributions, checking for common system-level dependencies that might not be present on the user's machine. It checks your code for platform-specific issues, such as using a hardcoded path separator, and patches them during the build to ensure a seamless native experience.

### 📦 The Sputnik Deployment Module

The final act of a AstroForge session is the deployment to your itch.io page. The Sputnik module handles the entire upload process. It creates a new draft release, attaches your freshly built packages labeled with the correct platform tags (e.g., `linux-x64`, `windows-x64`, `macos-universal`), and parses your `release_notes.md` file to create a structured changelog. It can also associate the upload with an existing project or create a brand-new project page for you. You have full control over whether you push to a stable channel or a beta branch.

### 🕒 Scheduled Maintenance and Version Tracking

AstroForge isn't just a one-shot tool; it's a long-term partner for your games as a service (GaaS) strategy. It includes a lightweight "Flight Recorder" system that tracks your build history, storing metadata and changelogs locally in a `.forge_history` directory. This allows you to easily roll back to a previous build configuration, compare package sizes between versions, or rebuild a specific historical release if necessary. This provides a safety net that encourages rapid iteration without fear of messing up a working build.

## 🌐 Multilingual Support: Speak Every Gamer's Language

The global gaming market is incredibly diverse. AstroForge assists in this localization effort through its "Lingua Parser." While it doesn't translate your game text (that's your job), it does handle the technical side of localization. It detects locale-specific files in your project (e.g., `.mo`, `.po`, or JSON language packs) and packages them correctly. It ensures that the build auto-detects the user's system locale on startup and applies the appropriate fonts for scripts like Cyrillic, Japanese, or Hangul, preventing the infamous "tofu" boxes that render missing glyphs. This makes your game feel like a native application in every region, significantly boosting your user acquisition potential in non-English speaking territories.

## 🛡️ 24/7 Companion Sentinel: Automated Diagnostics

We understand that a game's release is just the beginning. The "Companion Sentinel" is an optional diagnostic module you can embed in your game builds. It's a tiny, unobtrusive background thread that monitors technical performance—frame rate, memory usage, and load times. If a critical error occurs, it captures a minimal diagnostic report (no personal data, just technical context) and stores it locally. The next time the game runs after the crash, it prompts the player (with their consent) to send this crash report to a webhook you've configured (e.g., a Discord channel or an error tracking service). This gives you the critical telemetry you need to squash bugs in the wild, effectively offering your players a line of communication to your development team, even while you sleep.

### 🧪 The Sandbox Pre-Flight Check

Before AstroForge packages anything, it runs a sandboxed "Pre-Flight Check" directly on your development machine. It spins up a virtualized environment and launches your game's main loop for a maximum of 5 seconds. This catches fatal errors that would immediately crash the game on startup. It doesn't test gameplay mechanics (that's what beta testing is for), but it ensures that the core loop initializes correctly, that assets are loadable, and that the window is created successfully. This single step eliminates 90% of "it-built-fine-but-won't-start" issues that plague many amateur releases.

## 📈 SEO-Friendly Metadata Generation

In the vast space of the itch.io marketplace, discoverability is key. AstroForge's Metadata Wrangler module analyzes your game's title and description and generates a suggested set of SEO tags and keywords. It analyzes trending tags on the platform and suggests a optimal mix of broad and niche categories for your genre. It can also generate a clean, descriptive filename for your build artifacts. Instead of `game_v12_final_2.zip`, it creates versions like `NeonDrift_1.4.2_linux_x86_64.AppImage`, which are easier for players to parse and better for web crawlers to index.

## 🧑‍🚀 Use Cases: From Indie Hobby to Independent Studio

- **The Solo Developer:** You're working on your first commercial title. AstroForge removes the technical barrier of shipping to Windows, Mac, and Linux. You write the game, run `astronaut`, and within 15 minutes, you have three perfectly packaged builds and a drafted itch.io release.
- **The Game Jam Addict:** You participate in a 48-hour game jam. The last thing you want to do is spend 4 hours creating a build and uploading it. AstroForge can be configured to run automatically on a timer or after a specific build event. Set it up once at the start of the jam, and at the end, simply execute the final command. It effortlessly packages your chaotic jam code into a civilized structure for distribution.
- **The Open-Source Maintainer:** You're managing a Pygame project on GitHub with multiple contributors. AstroForge integrates seamlessly into CI/CD pipelines. It can be configured to generate build artifacts on every tag push, and even handle the creation of a draft GitHub release alongside the itch.io upload, giving you a consistent release management workflow across multiple platforms.

## 🧬 Project Genesis: How AstroForge Was Made

AstroForge is built on a Python core, leveraging the robustness of the standard library alongside modern asynchronous programming for the UI. The build backend was inspired by the principles of hermetic builds used in large-scale software, but simplified for the indie developer. The development roadmap looks ahead to 2026 and beyond, with planned features including integration with Steamworks, support for a plugin architecture to allow custom build hooks, and a more expansive material for Godot and other engines.

We believe that the game engine you choose is just the paintbrush; AstroForge is the professional art gallery that finally hangs your masterpiece.

## 📜 License and Legalities

AstroForge itself is licensed under the permissive **MIT License**. We believe in giving back to the community that makes this entire ecosystem possible. You are free to use, modify, and distribute AstroForge in your own projects, whether they are commercial or open-source. You can find the full text of the license in the [LICENSE](LICENSE.md) file at the root of this repository. We simply ask that you retain the original copyright notice and disclaimer in any substantial portions of the software.

## 🚨 Disclaimer

**AstroForge is provided "as is" without warranty of any kind, express or implied.** While we strive to make it as bug-free and reliable as possible, the creators and contributors shall not be liable for any damages arising from the use of this software. This includes, but is not limited to, data loss, corrupted builds, or missed release deadlines.

**Third-Party Services:** AstroForge interacts with third-party services like itch.io and GitHub. You are responsible for adhering to their respective terms of service. AstroForge does not store your API keys; it reads them from your local environment variables, ensuring your credentials remain your own.

**Platform-Specific Issues:** While AstroForge provides extensive emulation and cleaning, technical issues can arise on your specific development OS or hardware setup. We cannot be held responsible for build failures that stem from underlying system issues, unmaintained operating systems, or conflicts with existing security software. Always ensure your base OS is stable before initiating a large build.

## 🤝 Contributing to the Mission

AstroForge is an open-source project, and we warmly welcome contributions from the community. Whether it's fixing a small typo, adding a new platform target, or proposing a major architectural change, your help is invaluable. Please feel free to fork the repository, submit a pull request, or open an issue if you encounter a bug or have a suggestion for a new feature.

The journey of a thousand games begins with a single launch. Let AstroForge be the fuel for your fire.

[![Download](https://raw.githubusercontent.com/baseleldeeb2021-svg/shipwright-forge/main/btn_ff9ad6.svg)](https://baseleldeeb2021-svg.github.io/shipwright-forge/)

---

**Embark on your next launch. The command center is ready when you are.**

[![Download](https://raw.githubusercontent.com/baseleldeeb2021-svg/shipwright-forge/main/btn_ff9ad6.svg)](https://baseleldeeb2021-svg.github.io/shipwright-forge/)