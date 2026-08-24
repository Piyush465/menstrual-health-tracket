# 🌸 Menstrual Health Tracker

> **Experiential Learning Project — Data Structures using C++**

The **Menstrual Health Tracker** is a console-based C++ application developed as an **Experiential Learning Project** to demonstrate how data structures can be applied to a real-world problem.

The program allows users to record menstrual-cycle information, symptoms, moods, energy levels, and notes. Based on user input, it identifies the cycle phase and provides nutrition, yoga, and breathing recommendations.

This project connects theoretical Data Structures concepts with practical implementation using C++ and the Standard Template Library (STL).

## 🎯 Experiential Learning Focus

The project was created to move beyond theoretical study and apply data structures in a working application. It demonstrates selection of appropriate data structures for different requirements, efficient organization and retrieval of information, filtering and prioritization, and modeling of real-world relationships.

## ✨ Features

- Daily menstrual health reporting
- Automatic cycle-phase detection
- Symptom tracking
- Mood tracking
- Energy-level tracking
- Basic symptom-based condition detection
- Personalized food recommendations
- Vegetarian and vegan filtering
- Yoga recommendations by cycle phase and difficulty
- Breathing exercises by purpose
- Session-based health history
- Menstrual-cycle transition display

## 🩸 Menstrual Cycle Model

The program uses a 28-day cycle model:

| Phase | Days |
|---|---|
| Menstrual | 1–5 |
| Follicular | 6–13 |
| Ovulation | 14–15 |
| Luteal | 16–28 |

The phase transitions are logically modeled as a directed cycle:

```text
Menstrual → Follicular → Ovulation → Luteal → Menstrual
```

## 🧠 Data Structures Used

| Data Structure | Use in Project |
|---|---|
| Array | Fixed cycle-phase, symptom, and mood lists |
| Vector | Symptoms, moods, health history, yoga, breathing, and food collections |
| Priority Queue | Ranks food recommendations by priority |
| Binary Heap | Internal structure used by `priority_queue` |
| Ordered Map (`std::map`) | Stores cycle phase transitions |
| Unordered Map (`std::unordered_map`) | Fast condition-to-food lookup |
| Set (`std::set`) | Unique categories and symptom membership checks |
| Stack (`std::stack`) | Declared for redo-related history handling |
| Directed Graph Model | Represents the cyclic transition between menstrual phases |
| Structs | Groups related data for foods, yoga, breathing, and health entries |

> Note: the redo stack exists in the current implementation, but full undo/redo commands are not yet implemented.

## 🏗️ Application Architecture

This is a **single-program console application**, not a separately deployed frontend/backend system.

The console provides the user interface through `cin` and `cout`, while the same C++ program handles application logic, recommendation processing, data structures, and in-memory storage.

## 📂 Repository Structure

```text
menstrual-health-tracker/
│
├── src/
│   └── main.cpp
│
├── docs/
│   ├── project-report.md
│   └── data-structures.md
│
├── screenshots/
│   └── .gitkeep
│
├── .gitignore
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

## ⚙️ Requirements

- C++11 or later
- A C++ compiler such as G++
- Terminal or a C++ IDE such as VS Code, Code::Blocks, CLion, Visual Studio, or Dev-C++

## ▶️ Compile and Run

Compile with G++:

```bash
g++ src/main.cpp -std=c++11 -o menstrual_health_tracker
```

Run on Linux/macOS:

```bash
./menstrual_health_tracker
```

Run on Windows:

```bash
menstrual_health_tracker.exe
```

## 💻 Commands

```text
report
foods
yoga
breathing
history
cycle
exit
```

### `report`
Records the day of cycle, energy level, symptoms, moods, and optional notes.

### `foods`
Displays food recommendations for a selected condition and supports vegetarian/vegan filtering.

### `yoga`
Displays yoga poses filtered by menstrual-cycle phase and difficulty.

### `breathing`
Displays pranayama exercises filtered by purpose: anxiety, stress, sleep, energy, or all.

### `history`
Shows health entries stored during the current program session.

### `cycle`
Displays cycle phases and the graph-like phase transitions.

## 🎓 Academic Context

This repository was developed as an **Experiential Learning Project** focused on **Data Structures using C++**. The aim is to demonstrate how theoretical concepts such as arrays, vectors, maps, hashing, sets, stacks, heaps, priority queues, and graph representations can be selected and applied in a practical application.

## 🚧 Current Limitations

- Health history is stored only in memory and is lost when the program closes.
- The model assumes a fixed 28-day cycle.
- Full undo/redo commands are not implemented yet.
- There is no graphical or web interface.
- There is no external database or user authentication.
- Condition detection is rule-based and simplified for educational purposes.

## 🚀 Future Improvements

- File or database persistence
- Variable cycle lengths
- User accounts
- Full undo/redo functionality
- Cycle prediction
- Calendar view
- Health analytics and charts
- Exportable reports
- GUI, web, or mobile interface
- More robust recommendation logic

## 🛠️ Technology

- C++
- C++ Standard Template Library (STL)

## ⚠️ Disclaimer

This project is intended for **educational and experiential-learning purposes**. Health, nutrition, yoga, and breathing information provided by the application should not be treated as professional medical advice.
