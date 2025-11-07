
---

# 🧩 Simple TCP Time Server (`start.c`)

This project is a minimal **cross-platform TCP server** written in **C**.
It listens on **port 8080**, accepts a single incoming connection, and responds with the **current local time** as a simple **HTTP response**.

The code runs on both **Windows** and **Unix-like systems** (Linux/macOS).

---

## 🧠 Overview

`start.c` demonstrates how to set up a basic TCP server using sockets.
It covers the fundamental steps of network programming in C:

1. Initialize the socket API (`WSAStartup` on Windows).
2. Configure a local server address.
3. Create, bind, and listen on a socket.
4. Accept an incoming client connection.
5. Receive and print the client’s request.
6. Send a simple HTTP response containing the current local time.
7. Cleanly close all sockets and resources.

---

## ⚙️ Requirements

* A **C compiler** (`gcc`, `clang`, or MSVC`)
* Network access to **port 8080**
* Basic understanding of C and networking

---

## 🧩 Build Instructions

### 🖥️ Linux / macOS

```bash
gcc start.c -o start
./start
```

### 🪟 Windows (MinGW or Visual Studio)

Using **MinGW**:

```bash
gcc start.c -o start -lws2_32
```

Using **Visual Studio Developer Command Prompt**:

```bash
cl start.c ws2_32.lib
```

Then run:

```bash
start.exe
```

---

## 🌐 Usage

Once the server is running, open a browser or use `curl` to test it:

```bash
curl http://localhost:8080
```

You should see output similar to:

```
HTTP/1.1 200 OK
Connection: close
Content-Type: text/plain

Local time is: Fri Nov  7 15:42:16 2025
```

The console running `start.c` will display messages for each step (creating sockets, binding, waiting for connection, etc.).

---

## 📁 Project Structure

```
.
├── start.c     # The TCP time server source code
└── README.md   # Project documentation
```

---

## 🧾 License

This project uses the **MIT License**:

```
Copyright (c) 2018 Lewis Van Winkle
```

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is furnished to do so.

> See the full license header at the top of `start.c`.

---

## 💡 Notes

* This server handles **one client at a time** — perfect for learning purposes.
* To make it more robust, you can:

  * Add **multithreading** or **`select()`** for concurrent clients
  * Send formatted HTML or JSON responses
  * Include error logging and retry mechanisms

---

