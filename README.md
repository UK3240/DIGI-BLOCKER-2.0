# Block Diagram & Signal Flow Graph Reduction Tool

A complete full-stack application for creating, manipulating, and reducing block diagrams and signal flow graphs, similar to MATLAB's Simulink interface.

## Features

### Frontend (HTML/CSS/JavaScript)
- **Drag and Drop Interface**: Easily add blocks to the canvas
- **Advanced Features**:
  - Zoom in/out (Ctrl + mouse wheel)
  - Pan mode for navigation
  - Undo/Redo (Ctrl+Z, Ctrl+Y)
  - Save/Load diagrams
  - Real-time block and connection counters
- **Block Types**:
  - Basic Blocks: Gain, Summer (with positive/negative feedback), Integrator, Differentiator
  - Signal Flow Graph: Nodes and Branches
  - Input/Output blocks
- **Connection System**: Connect blocks with visual feedback
- **Properties Panel**: Edit block properties
- **Modern UI**: Clean, MATLAB-like interface

### Backend (Java Spring Boot)
- RESTful API for diagram persistence
- Graph reduction algorithms
- H2 database for data storage
- CORS enabled for frontend integration

## Project Structure

```
BDRT FRONTEND/
├── index.html          # Main HTML file
├── styles.css          # Styling
├── script.js           # Frontend logic
├── README.md           # This file
└── backend/            # Java Spring Boot backend
    ├── pom.xml
    ├── src/
    │   └── main/
    │       ├── java/com/bdrt/
    │       │   ├── controller/    # REST API
    │       │   ├── service/       # Business logic
    │       │   ├── model/         # Database entities
    │       │   └── dto/           # Data transfer objects
    │       └── resources/
    │           └── application.properties
    └── README.md
```

## Quick Start

### Frontend Only
1. Open `index.html` in a web browser
2. Start creating diagrams!

### Full Stack (Frontend + Backend)

#### 1. Start Backend Server
```bash
cd backend
mvn spring-boot:run
```
Server runs on `http://localhost:8080`

#### 2. Open Frontend
- Open `index.html` in a web browser
- Or serve it using a local server:
  ```bash
  # Using Python
  python -m http.server 8000
  
  # Using Node.js
  npx http-server
  ```

#### 3. Use Features
- **Save**: Click "Save" button to save diagram to backend
- **Load**: Click "Load" button to retrieve saved diagrams
- **Reduce**: Click "Reduce Graph" to apply reduction algorithms

## Keyboard Shortcuts

- **Ctrl+Z**: Undo
- **Ctrl+Y** or **Ctrl+Shift+Z**: Redo
- **Space**: Pan mode
- **Escape**: Exit pan mode
- **Delete**: Delete selected block
- **Ctrl + Mouse Wheel**: Zoom in/out

## API Endpoints

- `POST /api/diagrams` - Save diagram
- `GET /api/diagrams` - Get all diagrams
- `GET /api/diagrams/{id}` - Get diagram by ID
- `POST /api/reduce` - Reduce graph

## Technologies

### Frontend
- HTML5
- CSS3
- Vanilla JavaScript (ES6+)

### Backend
- Java 17
- Spring Boot 3.1.5
- Spring Data JPA
- H2 Database
- Maven

## Browser Compatibility

Works best on modern browsers:
- Chrome/Edge (recommended)
- Firefox
- Safari

## Development

### Backend Development
```bash
cd backend
mvn clean install
mvn spring-boot:run
```

### Frontend Development
- Edit `index.html`, `styles.css`, or `script.js`
- Refresh browser to see changes
- Check browser console for errors

## Future Enhancements

- Advanced graph reduction algorithms (Mason's gain formula)
- More block types (transfer functions, feedback loops)
- Export to different formats (PDF, SVG)
- Collaborative editing
- Real-time synchronization
- Advanced signal flow graph features

## Notes

- The backend server must be running for save/load/reduce features
- If backend is unavailable, save/load falls back to local storage
- Graph reduction uses simplified algorithms - can be extended with more sophisticated methods
