---
title: CollabTeX - Collaborative LaTeX Editor
summary: A peer-to-peer collaborative text editor that supports LaTeX compilation services and PDF previewing
tags:
  - TypeScript
  - Python
  - P2P
  - Real-time Collaboration
  - LaTeX
date: '2025-06-01'

# Optional external URL for project (replaces project detail page).
external_link: ''

image:
  caption: CollabTeX Editor Interface
  focal_point: Smart

links:
  - icon: globe
    icon_pack: fas
    name: Live Demo
    url: https://collabtex.com
  - icon: github
    icon_pack: fab
    name: Code
    url: https://github.com/JaedenRotondo/CollabTeX
  - icon: blog
    icon_pack: fas
    name: Blog Post
    url: '#'
  - icon: video
    icon_pack: fas
    name: Demo Video
    url: '#'

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ''
---

## Overview

CollabTeX is a cutting-edge peer-to-peer (P2P) collaborative text editor specifically designed for LaTeX document creation. Built with TypeScript and Python, it enables real-time collaboration without the need for a central server, ensuring privacy and efficiency.

## Key Features

- **Real-time P2P Collaboration**: Multiple users can edit documents simultaneously using Conflict-free Replicated Data Types (CRDTs)
- **LaTeX Compilation**: Integrated LaTeX compilation service with live PDF preview
- **Docker Integration**: Isolated build environments using Docker spawn builds
- **Offline Support**: Full functionality even when disconnected, with automatic sync when reconnected
- **Version Control**: Built-in document history and version tracking

## Technical Stack

### Frontend
- **SvelteKit**: Modern, reactive UI framework
- **TypeScript**: Type-safe development
- **IndexedDB**: Client-side storage for offline functionality

### Backend
- **Python**: LaTeX compilation service
- **SQLite**: Lightweight database for document metadata
- **Docker**: Containerized build environments

### Core Technologies
- **CRDTs**: For conflict-free collaborative editing
- **WebRTC**: P2P connection establishment
- **WebSockets**: Real-time communication fallback

## Architecture Highlights

The application uses a decentralized architecture where:
1. Each client maintains a local copy of the document
2. Changes are propagated through P2P connections using CRDTs
3. LaTeX compilation happens in isolated Docker containers
4. PDF preview is generated and streamed to all connected clients

This architecture ensures data privacy, reduces server costs, and provides excellent performance even with multiple concurrent users.