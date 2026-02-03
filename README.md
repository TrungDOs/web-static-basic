# Web Static Basic

A simple static web application serving a Memory Card Challenge game using Docker.

## Project Structure

```
web-static-basic/
├── Dockerfile          # Docker configuration to containerize the app
├── index.html          # Main HTML file with the Memory Card Challenge game
└── README.md           # This file
```

## Overview

This project contains a minimal static web application built with:
- **HTML/CSS/JavaScript** - The Memory Card Challenge game interface
- **Nginx** - Web server running inside a Docker container
- **Docker** - Containerization for easy deployment

## Getting Started

### Prerequisites
- Docker installed on your system

### How to Run

1. **Build the Docker image:**
   ```bash
   docker build -t web-static-basic .
   ```

2. **Run the container:**
   ```bash
   docker run -p 80:8080 web-static-basic
   ```
   Or with a custom port:
   ```bash
   docker run -p 8080:80 web-static-basic
   ```

3. **Access the application:**
   Open your browser and navigate to:
   - `http://localhost` (if using port 80)
   - `http://localhost:8080` (if using port 8080)

## Files Description

### Dockerfile
- Uses Nginx Alpine image (`nginx:1.28.0-alpine`) - lightweight and efficient
- Clears default Nginx content
- Copies `index.html` to the Nginx web root
- Exposes port 80
- Starts Nginx in foreground mode

### index.html
- Complete Memory Card Challenge game
- Features:
  - Interactive card matching game
  - Styled with modern CSS (Font: Inter)
  - Responsive grid layout
  - Score tracking (Matches, Attempts)
  - Vietnamese language support
  - Blue (#002182) and red (#e6202d) color scheme

## Game Features

- Memory-based card matching game
- Score tracking system
- Interactive card flip animations
- Clean, modern UI
- Language: Vietnamese

## Docker Details

- **Base Image:** nginx:1.28.0-alpine (minimal, ~40MB)
- **Port:** 80 (standard HTTP)
- **Content Location:** `/usr/share/nginx/html/`
- **Execution Mode:** Foreground daemon (proper Docker signal handling)

## Development

To modify the game:
1. Edit `index.html` directly
2. Rebuild the Docker image: `docker build -t web-static-basic .`
3. Run the new container

**Built with:** HTML5, CSS3, JavaScript, Nginx, Docker
