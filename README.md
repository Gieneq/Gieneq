# 👋 Hi, I'm Piotr!

I'm a systems engineer with an embedded background — now focused on **Rust backend, tooling, and systems development**.

To me, systems engineering means owning the full path: From hardware and firmware, through protocols and tooling, to services and user interfaces.  I've designed drivers, built cloud-connected firmware, created CLI and web tools, and automated real-world processes.

I began exploring Rust in 2023, and **since late 2024**, I’ve been coding in it 4–10 hours daily — both professionally and in personal projects. I’m now shifting fully into **Rust-focused roles** — backend services, infrastructure, or developer tooling — where I can apply the same precision and full-stack thinking embedded demanded, but in modern, scalable systems.

## 🦀 Why Rust?

- I love **type safety and reliability**
- I thrive in **low-level, performance-aware environments**
- I write **tested, maintainable code** with both unit and integration tests
- I enjoy building **tools and services that actually solve problems**
- And I’ve built **real systems** already — not tutorials

## 🦀 Rust Projects

Since 2023, I’ve been learning and building with Rust — both out of curiosity and to stay sharp while working in a company environment.

Starting in late 2024, I dedicated 4–10 hours daily to Rust development, creating production-grade tools for internal use and personal projects across backend, CLI, gamedev, and embedded domains.

My focus is on writing high-quality, maintainable code — backed by unit and integration tests — to automate processes, improve reliability, and reduce uncertainty.

### 🧩 [Multiplayer Hide&Seek Game](https://github.com/Gieneq/RustMultiplayer) (personal) 

<p align="center">
  <img alt="Starting 4 player hide&seek game" src="res/hide_n_seek_opening.gif">
  </br>
  <img alt="Gameplay hide&seek" src="res/hide_n_seek_gameplay.gif">
</p>
<p align="center">
  <em> Gameplay 4 players: 3 hiders one seeker </em>
</p>

> **Techs:** Rust, Tokio, TCP, Serde, WGPU, Clap, thiserror

**Key features:**
- Asynchronous server built with Tokio
- WGPU-powered game client with real-time rendering
- CLI client alternative
- TCP communication using a JSON-based protocol
- Fully tested: unit and integration tests for client–server interaction

<details>
  <summary>Details</summary>
  <p><strong>Overview</strong></p>
  <p>A multiplayer mini-game built from scratch in Rust, featuring a custom async game server and real-time graphical and CLI clients.  </p>
  <p>The game includes a lobby system, game state transitions, basic NPC behavior, and separate GUI roles depending on player type.</p>
  <p><strong>Project Scope</strong></p>
  <ul>
    <li>Async server handling multiple client connections and managing game world state </li>
    <li>In-game chat system distinguishing between server and client messages</li>
    <li>Shared client logic with both CLI and WGPU-based GUI frontends</li>
    <li>Decoupled client connections from in-game character state</li>
    <li>Procedural world generation</li>
    <li>Basic NPC AI logic and movement</li>
    <li>Game state transitions: lobby → active game → summary</li>
    <li>Reward system and scoring logic for winning players</li>
  </ul>
</details>

---

### 🧩 [Diamond Painting Generator](https://github.com/Gieneq/DiamondsImager) (personal) 

<p align="center">
  <img width="400" alt="Dithering image with palette" src="res/dithering_result.png">
</p>

> **Techs:** Rust, Axum, Serde, PDF, Clap, thiserror, palette, image

**Key features:**
- Uploads a source image
- Converts image into a printable diamond painting pattern
- Generates a DMC color palette and Bill of Materials
- *(Coming soon)* User accounts for project storage

<details>
  <summary>Details</summary>
  <p><strong>Overview</strong></p>
  <p>A personal project inspired by my wife’s hobby.</p>
  <p>Users can upload an image, select available DMC colors, and receive a ready-to-print pattern along with a Bill of Materials (BOM) listing all required diamond colors and quantities.</p>
  <p><strong>Project Scope</strong></p>
  <ul>
    <li>REST API with endpoints for uploading images and tracking processing status  </li>
    <li>Image analysis and dithering using DMC-compatible palettes  </li>
    <li>Color quantization and matching using perceptual color distance</li>
    <li>Generates high-resolution PDF output for printing </li>
    <li>Optional UI planned for future use</li>
  </ul>
</details>

---

### 🏭 [ARM GDB External Memory Loader](https://github.com/Gieneq/GDB-Loader) (company)

<p align="center">
  <img width="300" alt="Uploaded video to external FLASH NOR" src="res/uploaded_example _loader.gif">
</p>


> **Techs:** Rust, Tokio, Clap, thiserror, GDB

**Key features:**
- CLI tool to upload binary files to external memory via J-Link and GDB
- Interacts with GDB using subprocess communication
- Chunks binary files to match memory page alignment
- Supports uploading files up to 4MiB

<details>
  <summary>Details</summary>
  <p><strong>Overview</strong></p>
  <p>Command-line utility for uploading binary data to external NOR Flash on ARM-based devices using a J-Link debugging probe. </p>
  <p>The upload process is mediated through a dedicated C-based upload API integrated into the firmware, which is called directly from the host via GDB during a debug session.</p>
  <p><strong>Responsibilities</strong></p>
  <ul>
    <li>Studied and leveraged GDB’s ability to call target-resident C functions via `call` commands</li>
    <li>Wrote a set of C functions exposed in the target firmware to receive and write memory chunks</li>
    <li>Implemented GDB subprocess automation and communication from Rust</li>
    <li>Designed chunked, page-aligned transfer with status feedback</li>
    <li>Built a robust CLI around this mechanism for ease of use in production/test environments</li>
  </ul>
</details>

---

### 🏭 Sterilizers production testing backend (company)

> **Techs:** Rust, Actix-Web, Tokio, USB (CDC ACM), Modbus, Serde, Clap

**Key features:**
- Connects to sterilizers via USB Modbus
- Remote device control over serial and HTTP
- Logs and monitors sterilization process
- Functional testing and validation

<details>
  <summary>Details</summary>
  <p><strong>Overview</strong></p>
  <p>At the final stage of steam sterilizer production, each unit undergoes functionality testing.</p>
  <p>This Rust-based backend was developed as an experimental alternative to the existing Python backend, aiming to improve maintainability.</p>
  <p><strong>Responsibilities</strong></p>
  <ul>
    <li>Implemented Modbus communication over USB CDC ACM</li>
    <li>Designed an abstraction layer over Modbus to simplify device control</li>
    <li>Enabled remote control of multiple devices in parallel</li>
    <li>Integrated logging and monitoring of sterilization process data for QA</li>
  </ul>
</details>

## 🗃️ Past Engineering Projects

### 🏭 Internet-connected steam sterilizer firmware (company)

<p align="center">
  <img width="300" alt="Internet conneted steam sterilizer firmware" src="res/sterilizer.png">
</p>

> **Techs:** C, C++, RTOS, Azure IoT HUB/DPS, TouchGFX, MQTT, HTTP, WebSocket, CRUD, TLS, STM32, ESP32

**Key features:**
- Responsive modern HMI,
- Logging to USB MSC & cloud
- Sterilization process selection

<details>
  <summary>Details</summary>
  <p><strong>Overview</strong></p>
  <p>Firmware for an Internet-connected steam sterilizer. Responsible for end-to-end embedded system design, including control logic, connectivity, and modern responsible user interface.</p>
  <p><strong>Responsibilities</strong></p>
  <ul>
    <li>Low-level memory driver:
      <ul>
        <li>Shared FMC bus: NOR + PSRAM with Read/Write management</li>
        <li>Buffering and caching</li>
        <li>External memory loading</li>
        <li>Failsafe filesystem</li>
        <li>Fragmentation monitoring</li>
      </ul>
    </li>
    <li>WiFi connectivity:
      <ul>
        <li>Manage WiFi connection</li>
        <li>Register device in Azure DPS using HTTPS</li>
        <li>Send telemetry, chunking & receive notification from IoT Hub via MQTTS</li>
        <li>Monitor new firmware & do OTA updates with backup</li>
        <li>RED Directive & service tools</li>
      </ul>
    </li>
    <li>Implement HMI project:
      <ul>
        <li>Custom TouchGFX components</li>
        <li>Optimized rendering</li>
        <li>External double framebuffer, external graphics data, FLASH write operations management</li>
      </ul>
    </li>
    <li>Sterilization process control:
      <ul>
        <li>Implementation of PID and hysteresis</li>
        <li>Heaters, pumps, valves control</li>
        <li>Optimizing physical process for speed</li>
      </ul>
    </li>
    <li>USB dual-role:
      <ul>
        <li>Host MSC to store process data, download firmware</li>
        <li>Device CDC/ACM Modbus for production, testing, and service</li>
      </ul>
    </li>
    <li>LED strips:
      <ul>
        <li>RGB animations</li>
      </ul>
    </li>
  </ul>
</details>

### 🏭 [CMake & Dev Container steam sterilizer firmware](https://github.com/Gieneq/STM32U5_CMake_DevContainer_TouchGFX_Template) (company)

> **Techs:** C, C++, CMake, Google Test, Linker script, STM32U5, Docker, VS Code, GDB server

**Key features:**
- Full DevContainer setup to replace legacy IDEs like STM32CubeIDE
- Streamlined VS Code tasks and launch configurations for building, flashing, and debugging
- Remote debugging via external GDB server
- Unit tests runnable both on host (Google Test) and target
- CMake-based build system compatible with CubeMX and TouchGFX code generation

<details>
  <summary>Details</summary>
  <p><strong>Overview</strong></p>
  <p>Embedded projects are notoriously difficult to transfer between machines or contributors.  </p>
  <p>This setup isolates the entire development environment inside a Docker DevContainer, making the project reproducible and portable across systems.  </p>
  <p>It replaces heavier IDEs (e.g., Eclipse-based tools) with a modern, faster workflow using VS Code and Linux-based builds.</p>
  <p>Due to USB device mapping limitations in containers, the GDB server is run outside the container — but integrates cleanly with the VS Code debugging workflow.</p>
  <p><strong>Responsibilities</strong></p>
  <ul>
    <li>Indepth knowledge how ST-Link and J-Link works
    <li>Built a CMake-based project structure compatible with STM32CubeMX and TouchGFX codegen</li>
    <li>Integrated remote debugging through ST-Link and J-Link </li>
    <li>Wrote custom VS Code tasks and launch configurations for building, flashing, and testing</li>
    <li>Automated host-side unit tests with Google Test  </li>
    <li>Analyzed .elf and .map files to enable reliable external memory loading (NOR/PSRAM via FMC) using GDB</li>
    <li>Replaced legacy IDEs with reproducible, Docker-based environment  </li>
  </ul>
</details>

  ### 🧩 [WiFi AccessPoint E-Ink Image Frame](https://github.com/Gieneq/C3eInkFrame) (personal)

  <p align="center">
    <img width="300" alt="E-Ink image frame project" src="res/frame_outside.jpg">
  </p>

  > **Techs:** C, ESP-IDF, JavaScript, HTML/CSS, PNG, Dithering, Captive Portal

  **Key features:**
  - ESP32-C3-based image frame with E-Ink display
  - Hosts its own WiFi Access Point and web server
  - JavaScript-based captive portal with image preview and upload
  - Uploads, crops, and dithers PNG files in-browser
  - Renders processed image on the E-Ink display

  <details>
    <summary>Details</summary>
    <p><strong>Overview</strong></p>
    <p>A standalone E-Ink picture frame with built-in access point and web interface.  </p>
    <p>Designed to display user-uploaded images without needing external services.  </p>
    <p>The device serves a fully self-contained web app (HTML/CSS/JS), allowing users to crop, scale, dither, and upload images directly to the ESP32 for display.</p>
    <p><strong>Project Scope</strong></p>
    <ul>
      <li>Developed embedded web server with JavaScript-based frontend  </li>
      <li>Implemented captive portal for instant access after connecting  </li>
      <li>Created image processing pipeline: crop → grayscale → dithering → upload  </li>
      <li>Parsed and displayed PNG images on E-Ink display using custom rendering logic  </li>
      <li>Designed minimal, UI-first UX for non-technical users  </li>
    </ul>
  </details>

### 🧩 [Python RPG game approach](https://github.com/Gieneq/LochPythonRPG) (personal)

<p align="center">
  <img width="300" alt="Internet conneted steam sterilizer firmware" src="res/pythongame.gif">
</p>

> **Techs:** Python, PyGame, Tiled, TMX/TSX, Sprite animation, ECS-style design

**Key features:**
- Multilayer 2D RPG engine with animated pixel-art world
- Game object system using delegation over inheritance
- Custom property system for entity input, update, and render logic
- Support for TMX/TSX formats from Tiled map editor
- Collision system with object interaction and debug renderer
- Sprite + animation system with abstracted timing

<details>
  <summary>Details</summary>
    <p><strong>Overview</strong></p>
    <p>A 2D RPG engine inspired by classic top-down games like *Zelda*.  </p>
    <p>Built in Python with Pygame, it features a layered tile-based world, animated entities, and a component-driven object system. </p> 
    <p>While the project remains in development, it has laid a strong foundation for a full pixel-art RPG engine.</p>
    <p><strong>Project Scope</strong></p>
    <ul>
      <li>Implemented an extensible object model using Python properties and composition  </li>
      <li>Integrated TMX/TSX map parsing for Tiled-based level design  </li>
      <li>Built a collision system with layered obstacle detection and visual debugging  </li>
      <li>Developed pixel-art rendering pipeline with global scaling logic  </li>
      <li>Introduced modular animations and entity state management  </li>
      <li>Designed and integrated custom tilesets and graphics (WIP)</li>
    </ul>
</details>

### 🧩 [RGB Audio Spectrum Display](https://github.com/Gieneq/Audio-Spectrum-Display) (personal)

<p align="center">
  <img width="280" alt="Main RGB Spectrum Display" src="res/asd.PNG">
  <br />
  <img width="280" alt="LCD control unit for spectrum display" src="res/vis.PNG">
</p>
<p align="center">
  <em>30+ ⭐ on GitHub · Featured on Instructables with 36k+ views and 190+ likes  
  <a href="https://www.instructables.com/Audio-Spectrum-Display-ASDV10-ESP32-399-WS2812B/">See project on Instructables ↗</a></em>
</p>

> **Techs:** C, ESP-IDF, ESP32, DSP, FFT, RGB animation

**Key features:**
- Custom enclosure & matrix design
- Real-time analog/digital audio sampling
- FFT signal processing on microcontroller
- 399-pixel WS2812B RGB LED matrix with custom animation effects
- LCD HMI for gain adjustment and effect selection
- Fully custom PCB and 3D-printed enclosure
- Planned support for raw WiFi 802.11 audio streaming (in development)

<details>
  <summary>Details</summary>
  <p><strong>Overview</strong></p>
  <p>This project visualizes audio input using real-time FFT on an ESP32 platform, driving a 399-pixel RGB LED matrix with animated effects.  </p>
  <p>The latest version includes an LCD display for control and settings, making it fully standalone. </p> 
  <p>It’s designed for living room aesthetics, performance, and modular expandability — including future raw WiFi-based audio streaming directly to the device.</p>
  <p><strong>Project Scope</strong></p>
  <ul>
    <li>Designed signal chain for analog/digital audio sampling</li>
    <li>Wrote fixed-point FFT and windowing implementation (optimized for MCU)</li>
    <li>Implemented a visual engine for multiple spectrum and waveform styles</li>
    <li>Built a custom UI using LCD and rotary input</li>
    <li>Created enclosure using 3D printing and transparent paneling</li>
    <li>Managed timing, memory, and DMA for stable animation performance</li>
    <li>Shared project publicly with detailed build instructions and firmware</li>
  </ul>
</details>

### 🧩 Bluetooth Macro Keyboard (personal)

> **Techs:** C++, ESP32, Bluetooth

**Key features:**
- Custom-built keyboard with programmable macro keys
- Sends hotkey combinations via Bluetooth HID profile
- Configurable actions for productivity

<details>
  <summary>Details</summary>
  <p><strong>Overview</strong></p>
  <p>A compact, Bluetooth-enabled macro keyboard built using an ESP32 board.  </p>
  <p>Designed to trigger custom key sequences for automation, shortcuts, and productivity tasks.</p>
  <p><strong>Project Scope</strong></p>
  <ul>
    <li>Implemented HID over Bluetooth communication  </li>
    <li>Programmed hotkey mapping logic using C++</li>
  </ul>
</details>

### 🏭 Remote-Controlled Exploration Boat for Historical Research (company)

<p align="center">
  <img width="400" alt="Representative mine shaft view" src="res/repr_luban.PNG">
</p>
<p align="center">
  <em>Representative image. Similar view was recorded by our vessel inside the flooded shaft. <a href="https://gazetawroclawska.pl/eksploruja-sztolnie-ukryte-przez-hitlerowcow-w-1945-roku-czy-kamienna-gora-w-lubaniu-moze-skrywac-zloto-wroclawia/gh/c5-18644463"> Source: gazetawroclawska. </a></em>
</p>

> **Techs:** C++, Arduino, CAN, 3D design, 3D print, Camera, RC, LED lighting

**Key features:**
- Custom remote-controlled vessel designed for underground exploration
- Equipped with real-time video streaming and lighting
- Operated via CAN from 20 meters below surface level
- Designed for harsh, low-visibility flooded environments

<details>
  <summary>Details</summary>
  <p><strong>Overview</strong></p>
  <p>A commissioned project to explore a flooded mineshaft located ~20 meters underground in Lubań, Poland.  </p>
  <p>The vessel was designed to descend into the shaft via 10cm drill and transmit video footage for archaeological and safety assessment.</p>
  <p><strong>Project Scope</strong></p>
  <ul>
    <li>Designed custom electronics and control system for vessel navigation  </li>
    <li>Integrated video capture with LED lighting for visibility  </li>
    <li>Built a watertight enclosure and propulsion system (partially successful)  </li>
    <li>Supply power and control signals from the surface  </li>
    <li>Contributed to one of the first serious technical attempts to explore the shaft — later fully successful in follow-up expeditions</li>
  </ul>
</details>

### 🏭 Ink Stain Area Measurement Device for Printing Industry (freelance)

<p align="center">
  <img width="300" alt="Ink Stain Measurement Device 3D model" src="res/opencvtool.png">
</p>

> **Techs:** Python, OpenCV, Custom GUI, 3D Design, 3D Printing

**Key features:**
- Real-time image processing for stain area detection
- Automated measurement of ink wear on printing drums
- Physical device designed and 3D-printed for stable imaging conditions

<details>
  <summary>Details</summary>
    <p><strong>Overview</strong></p>
    <p>This project was commissioned by a printing company to simplify and speed up the process of evaluating wear on printing cylinders.  </p>
    <p>Previously, this required expensive equipment and manual measurements. The new solution involved a custom device with fixed camera distance and lighting conditions, paired with OpenCV-based analysis.</p>
    <p><strong>Responsibilities</strong></p>
    <ul>
      <li>Designed and 3D-printed a custom enclosure to maintain consistent camera positioning</li>
      <li>Implemented a Python + OpenCV script to calculate ink stain surface area</li>
      <li>Tuned thresholding, perspective correction, and region isolation for robustness</li> 
      <li>Delivered an affordable and replicable device that reduced measurement time and cost</li>
    </ul>
</details>

### 🧩 GQuarter: [Custom 2D Game Engine & Editor](https://github.com/Gieneq/GQuarter) (2 years, personal)

<p align="center">
  <img width="300" alt="GQuarter engine terrain and water rendering" src="res/3dgame.png">
</p>

> **Techs:** Java, LWJGL (OpenGL), Custom GUI, 3D rendering, Shaders

**Key features:**
- Custom game loop and rendering pipeline (OpenGL + GLSL shaders)
- Basic 3D graphics algorithms and scene graph structure
- Mipmapping, geomipmapping, fresnel effect, bloom, skybox
- Entity-Component System for object behavior and modularity
- Audio system for positional 3D sound playback
- Input system with mouse and keyboard support
- Integrated level editor with in-engine GUI

<details>
  <summary>Details</summary>
    <p><strong>Overview</strong></p>
    <p> A custom game engine and level editor built in Java using OpenGL and LWJGL. Developed over 2 years as a personal challenge to understand real-time rendering, ECS-like architecture, and cross-cutting systems like audio, terrain generation, and GUI handling. </p>
    <p> The project helped me explore full-engine architecture and taught me key lessons about code structure, coupling, and the value of testing and separation of concerns. </p> 
    <p> Heavily inspired by <a href="https://www.youtube.com/@ThinMatrix">ThinMatrix YouTube series</a>. </p> 
    <p><strong>Project Scope</strong></p>
    <ul>    
      <li>Custom OpenGL rendering pipeline and shader management</li>
      <li>Entity system for managing in-game objects</li>
      <li>Terrain rendering and water effects</li>
      <li>GUI and event system for in-engine editor tools</li>
      <li>Scene serialization and reloading</li>
      <li>Basic audio and camera logic</li>
    </ul>
</details>

### 🧩 (2011) Hexapod robot with Bluetooth control (personal)

<p align="center">
  <img width="300" alt="Walking hexapod remote controller robot" src="res/robot.png">
</p>

<p align="center">
  <a href="https://www.youtube.com/watch?v=l720J65UCUo">
    <img width="300" alt="Walking hexapod remote controller robot" src="https://img.youtube.com/vi/l720J65UCUo/hqdefault.jpg">
  </a>
</p>
  
<p align="center">
  <em><a href="https://www.youtube.com/watch?v=l720J65UCUo">Competition video</a> – Wrocław University of Science and Technology</em>
</p>

[📺 National TV feature – TVP Info](https://www.youtube.com/watch?v=HK7IooV7AvY&ab_channel=TVPInfo)

> **Techs:** C++, Arduino, Inverse kinematics, Bluetooth

**Key features:**
- Custom mechanical design
- 3 degrees of freedom per leg
- Inverse kinematics for smooth body and leg motion
- Bluetooth-controlled via Android app
- Basic autonomous behavior using proximity sensors

<details>
  <summary>Details</summary>
    <p><strong>Overview</strong></p>
    <p>
      A six-legged walking robot designed and built in high school — combining mechanical engineering, embedded software, and robotics.
    The project earned awards at robotics tournaments and received national media coverage.
    </p>
    <p><strong>Project Scope</strong></p>
    <ul>
      <li>Designed mechanical structure for body and 6 legs</li>
      <li>Wrote control algorithms for inverse kinematics and walking gait</li>
      <li>Implemented Bluetooth communication protocol</li>
      <li>Implemented basic autonomous behavior using sensor feedback (feet and head proximity)</li>
    </ul>
</details>





