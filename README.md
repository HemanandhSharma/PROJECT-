README.md
AI Framework for UEBA — Web Interface

This project provides a lightweight, interactive web UI for experimenting with and visualizing elements of a UEBA (User and Entity Behavior Analytics) framework.
It includes:

A sliding configuration panel

A dynamic reports workspace

A floating, draggable chat assistant with two modes

A responsive layout that updates automatically when elements move or open/close

The entire interface is built using HTML, CSS, and vanilla JavaScript, with no external dependencies.

📌 Features
🔧 1. Input / Configuration File Panel

A collapsible sidebar for uploading files used in UEBA data pipelines:

.yaml configuration files

.txt or .log files

.csv datasets

The panel slides in from the left and automatically resizes the reports area.

📊 2. Dynamic Reports Section

A central display pane used for:

Viewing generated reports

Displaying results from pipeline jobs

Showing alerts or UEBA analytics

It expands or shrinks depending on:

Whether the input panel is open

Whether the floating chat panel is expanded

The chat window’s dragged location

Browser window resizing

💬 3. Floating, Draggable AI Chat Panel

A right-side chat assistant window with:

Click-to-expand bubble button

Smooth scale-in/out animations

Drag-anywhere movement using mouse

Two separated chat modes:

Pipeline data (chatA)

Interactive (chatB)

Independent message histories per mode

Clean message bubble UI

Auto-scroll behavior

“Enter to send” support

The chat window adapts dynamically to screen boundaries and updates the reports workspace size.

📁 Project Structure
.
├── index.html        # Contains HTML, CSS, and JS for the UI
└── README.md         # Documentation

🚀 Getting Started
1. Download or copy the index.html file

No frameworks, servers, or installs required.

2. Open the file in your browser

Just double-click the file or open via:

file:///path/to/index.html


You're ready to go.

🧩 Code Overview
Layout Components

#popupPanel — Left sliding input/config panel

#reports — Main workspace for generated reports

#floatingChat — Draggable chat assistant

#chatToggleBtn — Expand/collapse chat button

Drag Handling Logic

Implemented using raw JavaScript:

document.querySelector("#floatingChat h2").addEventListener('mousedown', e => {
    isDragging = true;
    offsetX = e.clientX - chatPanel.offsetLeft;
    offsetY = e.clientY - chatPanel.offsetTop;
});


Mouse movement updates the window position while keeping it within screen bounds.

Chat System

Each mode has its own chat container:

<div id="chatA"></div>
<div id="chatB"></div>


Messages are appended dynamically:

function addMessage(msg, type) {
    const chatWin = document.getElementById("chat" + currentMode);
}

🎨 Customization
Colors

Modify theme colors inside the CSS section:

background: #000;
background: white;
background-color: #007BFF;

Chat panel width

Adjust:

width: 33vw;
max-width: 600px;
min-width: 350px;

Animations

Modify transition timing:

transition: transform 0.5s ease;
transition: left 0.3s ease;

🛠 Suggested Enhancements

If you plan to extend this UI:

File parser for YAML, CSV, log files

Real backend chat integration (REST, WS, or LLM API)

UEBA pipeline execution integration

Report generator module

Save chat history to localStorage

Theme switcher (dark/light)

📜 License

You may add any open-source license (MIT recommended).
If you'd like me to generate one, just ask.

If you'd like a version with separated CSS/JS files, a diagram, or a project folder structure, I can produce it.
