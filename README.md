# SysForge – Windows System Utility

SysForge is a multi-threaded Windows desktop utility built with a single-window interface containing three simultaneously active tabs. Each tab interacts with the OS in real time using Windows APIs, ensuring continuous background operation even when switching tabs.

## Features
# Tab 1 — Monitor 
Live CPU usage (per-core + overall)
RAM usage (MB + %)
Total RAM (static)
Auto-refresh every 500ms
Timestamp of last update
Real OS data via PDH / GetSystemTimes / psutil

## Threading Model
Dedicated polling thread (500ms interval)
Data passed safely to GUI (message queue / queue.Queue)
GUI only renders data (no direct system calls)

## Stress Test
Launches threads equal to CPU cores
Simulates 100% CPU load for 10s
Verifies real-time monitoring accuracy

# Tab 2 — Controller
List of running processes
Controls: launch, pause, resume, kill
Real-time process management

# Tab 3 — Cleaner
Parallel scan of temp/cache directories
Displays file list
Selective file deletion
Technical Highlights
Multi-threaded architecture
Non-blocking GUI design
Real-time OS interaction via Windows APIs
Safe thread-to-GUI communication
