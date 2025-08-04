# Dungeon Escape

A console-based dungeon crawler game built in C++ using Object-Oriented Programming principles and the PDCurses library for terminal UI. This project was developed as an academic assignment for an Object-Oriented Programming course.

## Key Highlights

- **Full OOP Implementation**: Demonstrates inheritance, polymorphism, encapsulation, and abstraction
- **Dynamic Memory Management**: Proper allocation and deallocation of game objects
- **Template Programming**: Generic inventory system using C++ templates
- **Data Structures**: Custom implementations of queues and dynamic arrays
- **Terminal UI**: Multi-window interface using PDCurses library

## Features

### Gameplay Features

- Three interconnected rooms with unique challenges and rewards  
- Turn-based combat system with enemy encounters  
- Inventory management system with weapons, food, and keys  
- Dynamic health system with food-based healing  
- Key-based room unlocking mechanism

### Technical Features

- Multi-window terminal UI using PDCurses  
- Color-coded interface for clarity  
- Real-time updates to inventory and status  
- Exception handling for game-ending scenarios  
- Manual cleanup of dynamically allocated objects

## Object-Oriented Design

### Core Classes and Relationships

```
RoomElements (Abstract Base Class)
├── Enemy
├── Weapon
└── Food

Player
└── PlayerInventory
    ├── Inventory<Weapon>
    ├── Inventory<Food>
    └── Keys[3]

Room
├── ElementQueue
└── Room Navigation (Doubly Linked List)

Dungeon (Main Game Controller)
├── Player
├── Room Management
└── UI Management
```

### OOP Principles Demonstrated

1. **Inheritance**: Enemy, Weapon, and Food inherit from RoomElements  
2. **Polymorphism**: Virtual destructors and dynamic casting for element handling  
3. **Encapsulation**: Private data members with public accessor methods  
4. **Abstraction**: Abstract base class RoomElements defines a common interface  
5. **Templates**: Generic Inventory<T> class for type-safe storage  
6. **Operator Overloading**: Custom operators for comparing weapons and food

## Prerequisites

### Development Environment

- **Compiler**: MinGW-w64 GCC (recommended) or Visual Studio  
- **IDE**: Visual Studio Code (recommended)  
- **Library**: PDCurses 3.9 for Windows  
- **OS**: Windows

### Required Tools

- Git  
- Windows terminal or command prompt  
- Text editor or IDE with C++ support

## Installation & Setup

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd dungeon_escape
   ```

2. **Install PDCurses**:
   - Download PDCurses 3.9 for Windows
   - Extract to `C:\PDCurses-3.9\`
   - Ensure the library files are in the correct path

3. **Open in VS Code**:
   ```bash
   code .
   ```

## Compilation

### Using VS Code

1. Open the project folder in VS Code  
2. Use `Ctrl+Shift+P` and select "Tasks: Run Build Task"  
3. The executable `dungeon_escape.exe` will be created

### Manual Compilation

```bash
g++ -fdiagnostics-color=always -g main.cpp Dungeon.cpp ElementQueue.cpp Enemy.cpp Food.cpp Player.cpp PlayerInventory.cpp Room.cpp RoomElements.cpp Weapon.cpp -o dungeon_escape.exe -I"C:\PDCurses-3.9\PDCurses-3.9" -L"C:\PDCurses-3.9\PDCurses-3.9\wincon" -l:pdcurses.a
```

### Build Configuration

- Includes a `tasks.json` file for VS Code with pre-configured settings
- Debugging and diagnostics flags included
- Paths configured for header files and library

## How to Play

1. Run `dungeon_escape.exe`
2. Read the welcome instructions
3. Begin in Room 1

### Controls
- **Numbers (1-9)**: Select options
- **Y/N**: Confirm or decline actions
- **Any Key**: Continue through dialogue

### Objective
Progress through all three rooms, defeat enemies, manage resources, and survive until the end.

## Game Mechanics

### Combat System
- Turn-based combat between player and enemy
- Weapon selection from inventory
- Damage calculation based on weapon stats
- Food used for healing during or after combat

### Inventory System
- Weapons sorted using insertion sort based on damage
- Food sorted using shell sort based on healing value
- Keys used automatically when entering new rooms
- Dynamic resizing of inventory arrays

### Room Progression
- Rooms follow a linear sequence (1 → 2 → 3)
- Keys required to unlock each subsequent room
- Backtracking is allowed
- Completed rooms cannot be re-entered

## Project Structure

```
repository/
├── .vscode/
│   └── tasks.json                 # VS Code build configuration
└── dungeon_escape/
    ├── main.cpp                   # Entry point and game initialization
    ├── Dungeon.cpp/.hpp           # Main game controller
    ├── Player.cpp/.hpp            # Player class implementation
    ├── PlayerInventory.cpp/.hpp   # Player inventory management
    ├── Room.cpp/.hpp              # Room structure and navigation
    ├── ElementQueue.cpp/.hpp      # Queue for room elements
    ├── RoomElements.cpp/.hpp      # Abstract base class
    ├── Enemy.cpp/.hpp             # Enemy class implementation
    ├── Weapon.cpp/.hpp            # Weapon class implementation
    ├── Food.cpp/.hpp              # Food class implementation
    └── Inventory.hpp              # Template-based inventory system
```

## Technical Implementation

### Data Structures
- **Doubly Linked List** for room navigation
- **Queue** for managing room elements
- **Dynamic arrays** in the inventory system
- **Boolean arrays** for tracking key possession

### Algorithms
- **Insertion Sort** for weapon sorting
- **Shell Sort** for food sorting
- **Manual memory management** with destructors

### Design Patterns
- **Template Pattern** for generic inventory
- **Factory Pattern** for creating room elements
- **Observer Pattern** for UI updates during gameplay

### Memory Management
- **RAII principle** for safe memory usage
- **Destructors** ensure cleanup of dynamic objects
- **Exception handling** maintains application stability

## Contributing

This is an academic project. If you'd like to contribute or suggest improvements:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request
