# 👋 Hi, I'm Piotr!

I'm an engineer with a deep background in embedded RTOS systems, now fully driving into the world of Rust. Currently focusing on Rust — backend, tooling, and systems programming.

## 🦀 Rust Projects

Since 2023, I’ve been learning and building with Rust — both out of curiosity and to stay sharp while working in a company environment.

Starting in late 2024, I dedicated 4–10 hours daily to Rust development, creating production-grade tools for internal use and personal projects across backend, CLI, gamedev, and embedded domains.

My focus is on writing high-quality, maintainable code — backed by unit and integration tests — to automate processes, improve reliability, and reduce uncertainty.

### 🧩 [Multiplayer Hide&Seek Game](https://github.com/Gieneq/RustMultiplayer) (personal) 

> **Techs:** Rust, Tokio, TCP, Serde, WGPU, Clap, thiserror

**Key features:**
- Asynchronous server built with Tokio
- WGPU-powered game client with real-time rendering
- CLi client alternative
- TCP communication using a JSON-based protocol
- Fully tested: unit and integration tests for client–server interaction

<details>
  <summary>Details</summary>
    #### Overview
    A multiplayer mini-game built from scratch in Rust, featuring a custom async game server and real-time graphical and CLI clients.  
    The game includes a lobby system, game state transitions, basic NPC behavior, and separate GUI roles depending on player type.

    #### Project Scope
    - Async server handling multiple client connections and managing game world state 
    - In-game chat system distinguishing between server and client messages
    - Shared client logic with both CLI and WGPU-based GUI frontends
    - Decoupled client connections from in-game character state
    - Procedural world generation
    - Basic NPC AI logic and movement
    - Game state transitions: lobby → active game → summary
    - Reward system and scoring logic for winning players
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
    #### Overview
    A personal project inspired by my wife’s hobby.
    Users can upload an image, select available DMC colors, and receive a ready-to-print pattern along with a Bill of Materials (BOM) listing all required diamond colors and quantities.

    #### Project Scope
    - REST API with endpoints for uploading images and tracking processing status  
    - Image analysis and dithering using DMC-compatible palettes  
    - Color quantization and matching using perceptual color distance
    - Generates high-resolution PDF output for printing 
    - Optional UI planned for future use
  
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
    #### Overview
    Command-line utility for uploading binary data to external NOR Flash on ARM-based devices using a J-Link debugging probe. 
    The upload process is mediated through a dedicated C-based upload API integrated into the firmware, which is called directly from the host via GDB during a debug session.

    #### Responsibilities
    - Studied and leveraged GDB’s ability to call target-resident C functions via `call` commands
    - Wrote a set of C functions exposed in the target firmware to receive and write memory chunks
    - Implemented GDB subprocess automation and communication from Rust
    - Designed chunked, page-aligned transfer with status feedback
    - Built a robust CLI around this mechanism for ease of use in production/test environments

</details>

---

### 🏭 Sterilizers production testing backend (company)

> **Techs:** Rust, Actix-Web, Tokio, USB (CDC ACM), Modbus, Serde, Clap

**Key features:**
- Connects to sterilizers via USB Modbus
- Remote device control over serial and HTTP
- Control the device remotely
- Logs and monitors sterilization process
- Functional testing and validation

<details>
  <summary>Details</summary>
    #### Overview
    At the final stage of steam sterilizer production, each unit undergoes functionality testing.
    This Rust-based backend was developed as an experimental alternative to the existing Python backend, aiming to improve maintainability.

    #### Responsibilities
    - Implemented Modbus communication over USB CDC ACM
    - Designed an abstraction layer over Modbus to simplify device control
    - Enabled remote control of multiple devices in parallel
    - Integrated logging and monitoring of sterilization process data for QA
  
</details>

---

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
    #### Overview
    Firmware for an Internet-connected steam sterilizer. Responsible for end-to-end embedded system design, including control logic, connectivity, and modern responsible user interface.

    #### Responsibilities
    - Low level memory driver:
      - Shared FMC bus: NOR + PSRAM with Read/Write managment
      - Buffering and caching
      - External memory loading
      - Failsafe filesystem
      - Fragmentation monitoring
    - WiFi connectivity:
      - Manage WiFi connection
      - Register device in Azure DPS using HTTPS
      - Send telementry, chunking & receive notification from IoT Hub via MQTTS
      - Monitor new firmware & do OTA updates with backup
      - RED Directive & service tools
    - Implement HMI project:
      - Custom TouchGFX components
      - Optimized rendering
      - External doubleframebuffer, external graphics data, FLASH write operations managment
    - sterilization process control:
      - Implementation PID / histheresis
      - Heaters, pumps, valves control
      - Optimization physical process for speed
    - USB dualrole:
      - Host MSC to store processes data, download firmware
      - Device CDC/ACM Modbus for production, testing and service
    - LED strips:
      - RGB animations
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
    #### Overview
    Embedded projects are notoriously difficult to transfer between machines or contributors.  
    This setup isolates the entire development environment inside a Docker DevContainer, making the project reproducible and portable across systems.  
    It replaces heavier IDEs (e.g., Eclipse-based tools) with a modern, faster workflow using VS Code and Linux-based builds.
    
    Due to USB device mapping limitations in containers, the GDB server is run outside the container — but integrates cleanly with the VS Code debugging workflow.


    #### Responsibilities
    - Indepth knowledge how ST-Link and J-Link works
    - Built a CMake-based project structure compatible with STM32CubeMX and TouchGFX codegen
    - Integrated remote debugging through ST-Link and J-Link 
    - Wrote custom VS Code tasks and launch configurations for building, flashing, and testing
    - Automated host-side unit tests with Google Test  
    - Analyzed .elf and .map files to enable reliable external memory loading (NOR/PSRAM via FMC) using GDB
    - Replaced legacy IDEs with reproducible, Docker-based environment  
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
      #### Overview
      A standalone E-Ink picture frame with built-in access point and web interface.  
      Designed to display user-uploaded images without needing external services.  
      The device serves a fully self-contained web app (HTML/CSS/JS), allowing users to crop, scale, dither, and upload images directly to the ESP32 for display.

      #### Project Scope
      - Developed embedded web server with JavaScript-based frontend  
      - Implemented captive portal for instant access after connecting  
      - Created image processing pipeline: crop → grayscale → dithering → upload  
      - Parsed and displayed PNG images on E-Ink display using custom rendering logic  
      - Designed minimal, UI-first UX for non-technical users  
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
    #### Overview
    A 2D RPG engine inspired by classic top-down games like *Zelda*.  
    Built in Python with Pygame, it features a layered tile-based world, animated entities, and a component-driven object system.  
    While the project remains in development, it has laid a strong foundation for a full pixel-art RPG engine.

    #### Project Scope
    - Implemented an extensible object model using Python properties and composition  
    - Integrated TMX/TSX map parsing for Tiled-based level design  
    - Built a collision system with layered obstacle detection and visual debugging  
    - Developed pixel-art rendering pipeline with global scaling logic  
    - Introduced modular animations and entity state management  
    - Designed and integrated custom tilesets and graphics (WIP)
</details>

### 🧩 [RGB Audio Spectrum Display](https://github.com/Gieneq/Audio-Spectrum-Display) (personal)

<p align="center">
  <img width="280" alt="Main RGB Spectrum Display" src="res/asd.png">
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
    #### Overview
    This project visualizes audio input using real-time FFT on an ESP32 platform, driving a 399-pixel RGB LED matrix with animated effects.  
    The latest version includes an LCD display for control and settings, making it fully standalone.  
    It’s designed for living room aesthetics, performance, and modular expandability — including future raw WiFi-based audio streaming directly to the device.

    #### Project Scope
    - Designed signal chain for analog/digital audio sampling
  - Wrote fixed-point FFT and windowing implementation (optimized for MCU)
  - Implemented a visual engine for multiple spectrum and waveform styles
  - Built a custom UI using LCD and rotary input
  - Created enclosure using 3D printing and transparent paneling
  - Managed timing, memory, and DMA for stable animation performance
  - Shared project publicly with detailed build instructions and firmware
</details>

### 🧩 Bluetooth Macro Keyboard (personal)

> **Techs:** C++, ESP32, Bluetooth

**Key features:**
- Custom-built keyboard with programmable macro keys
- Sends hotkey combinations via Bluetooth HID profile
- Configurable actions for productivity

<details>
  <summary>Details</summary>
    #### Overview
    A compact, Bluetooth-enabled macro keyboard built using an ESP32 board.  
    Designed to trigger custom key sequences for automation, shortcuts, and productivity tasks.

    #### Project Scope
    - Implemented HID over Bluetooth communication  
    - Programmed hotkey mapping logic using C++
</details>

### 🏭 Remote-Controlled Exploration Boat for Historical Research (company)

<p align="center">
  <img width="400" alt="Representative mine shaft view" src="res/repr_luban.png">
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
    #### Overview
    A commissioned project to explore a flooded mineshaft located ~20 meters underground in Lubań, Poland.  
    The vessel was designed to descend into the shaft via 10cm drill and transmit video footage for archaeological and safety assessment.

    #### Project Scope
    - Designed custom electronics and control system for vessel navigation  
    - Integrated video capture with LED lighting for visibility  
    - Built a watertight enclosure and propulsion system (partially successful)  
    - Supply power and control signals from the surface  
    - Contributed to one of the first serious technical attempts to explore the shaft — later fully successful in follow-up expeditions
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
    #### Overview
    This project was commissioned by a printing company to simplify and speed up the process of evaluating wear on printing cylinders.  
    Previously, this required expensive equipment and manual measurements. The new solution involved a custom device with fixed camera distance and lighting conditions, paired with OpenCV-based analysis.

    #### Requirements
    - Designed and 3D-printed a custom enclosure to maintain consistent camera positioning  
    - Implemented a Python + OpenCV script to calculate ink stain surface area  
    - Tuned thresholding, perspective correction, and region isolation for robustness  
    - Delivered an affordable and replicable device that reduced measurement time and cost
</details>

### 🧩 GQuarter: Custom 2D Game Engine & Editor (2 years, personal)

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
    #### Overview
    A custom game engine and level editor built in Java using OpenGL and LWJGL. Developed over 2 years as a personal challenge to understand real-time rendering, ECS-like architecture, and cross-cutting systems like audio, terrain generation, and GUI handling.

    The project helped me explore full-engine architecture and taught me key lessons about code structure, coupling, and the value of testing and separation of concerns.

    Heavily inspired by [ThinMatrix YouTube series](https://www.youtube.com/@ThinMatrix).

    #### Project Scope
    - Custom OpenGL rendering pipeline and shader management
    - Entity system for managing in-game objects
    - Terrain rendering and water effects
    - GUI and event system for in-engine editor tools
    - Scene serialization and reloading
    - Basic audio and camera logic
</details>

### 🧩 (2011) Hexapod robot with Bluetooth control (personal)

<p align="center">
  <img width="300" alt="Walking hexapod remote controller robot" src="res/robot.png">
</p>

> **Techs:** C++, Arduino, Inverse kinematics, Bluetooth

**Key features:**
- Custom mechanical design
- 3 degrees of freedom per leg
- Inverse kinematics for smooth body and leg motion
- Bluetooth-controlled via Android app
- Basic autonomous behavior using proximity sensors

<details>
  <summary>Details</summary>
    #### Overview
    A six-legged walking robot designed and built in high school — combining mechanical engineering, embedded software, and robotics.
    The project earned awards at robotics tournaments and received national media coverage.

    #### Project Scope
    - Designed mechanical structure for body and 6 legs
    - Wrote control algorithms for inverse kinematics and walking gait
    - Apply Bluetooth communication protocol
    - Implemented basic autonomous behavior using sensor feedback (feet and head proximity)
</details>





