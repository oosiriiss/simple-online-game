# 🕹️ Distributed Game — Networked Multiplayer Game using C++ and Sockets

This project is a simple distributed multiplayer game developed as part of the **Distributed Computing** course. It demonstrates basic network communication and concurrency in C++ using TCP sockets. I also implemented a **really** basic IMGUI system. The code quality of some parts of this project is definitely something that could be worked on, but during the development there was a really busy semester at my university so I decided to finish all the features as quickly as possible while sacrificing maintainability and readability.


![Game](/imgs/gameplay.png)

---

## 📋 Requirements

To build and run the project, the following tools are required:

* **Linux system** (tested on Arch Linux)
* **CMake** – for generating build files
* **Ninja** – build system (optional if compiling manually)
* **g++** – or any other compiler with **C++23 support**
* **tmux** – for splitting one terminal into 3 windows (optional)

---

## 🚀 Quick Start (Using Script)

The easiest way to build and run the game is by using the provided script. It will compile the project and launch the application instances.

From the root of the cloned repository, run:

```bash
mkdir build && cd build && cmake .. -G Ninja && ln -sf ../assets ./assets && cd .. && ./run.sh
```

Make sure `run.sh` has executable permissions and a build directory with build files was generated (by cmake):

```bash
chmod +x run.sh
```

This script opens `tmux` with 3 windows:

* 1 for the server
* 2 for clients

---

## 🛠️ Manual Build Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/oosiriiss/simple-online-game.git
cd distributed-game
```

### 2. Generate Build Files (Using CMake + Ninja)

```bash
mkdir build && ln -sf ../assets ./assets
cd build
cmake .. -G Ninja
```

### 3. Compile the Project

```bash
ninja
```

After a successful build, the `build/` directory will contain:

* `executable-debug`
* `executable-release`

---

## 🔹 Manual Launch Instructions

### 1. Verify Port Availability

Ensure that **port `63921`** is not in use. This port is used by the server.

To change the port, edit the function `Application::run` in `Application.cpp`, then recompile the project.

### 2. Run Application Instances

You will need to run **3 instances** of the application:

```bash
# In Terminal Window 1 – Server
./build/executable-release server

# In Terminal Window 2 – Client 1
./build/executable-release

# In Terminal Window 3 – Client 2
./build/executable-release
```

> You can also use `executable-debug` if you prefer the debug version.

---

## 📞 Networking Info

* The game communicates over **TCP sockets**
* Server listens on port **63921** by default
* Clients connect to the server on startup

---

## 📚 License

This project is for educational purposes as part of university coursework. You may do whatever you want as long as you comply with the license :)


