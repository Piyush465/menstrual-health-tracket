# Menstrual Health Tracker — Project Report

## 1. Introduction to the Project

The **Menstrual Health Tracker** is a console-based application developed using C++ as an **Experiential Learning Project**. The project demonstrates how theoretical concepts from Data Structures can be applied to a practical health and wellness application.

The program allows users to record menstrual-cycle information, symptoms, moods, energy levels, and notes. It determines the menstrual-cycle phase from the day of the cycle, performs simple condition detection based on symptoms, and provides food, yoga, and breathing recommendations.

The project combines application logic with C++ Standard Template Library data structures such as arrays, vectors, maps, unordered maps, sets, stacks, and priority queues.

## 2. Objectives

- Develop a functional console-based menstrual health tracking application using C++.
- Apply theoretical Data Structures concepts to a real-world problem.
- Track symptoms, moods, cycle day, energy levels, and notes.
- Automatically determine the menstrual-cycle phase.
- Detect a simplified health condition based on selected symptoms.
- Provide prioritized food recommendations.
- Filter food recommendations according to vegetarian and vegan preferences.
- Recommend yoga poses according to cycle phase and difficulty.
- Recommend breathing exercises according to purpose.
- Demonstrate efficient storage, lookup, traversal, and prioritization using appropriate data structures.

## 3. Methodology

The application follows a command-driven console approach. When the program starts, the user is shown commands for reporting health information, viewing food recommendations, yoga poses, breathing exercises, health history, and menstrual-cycle information.

For a daily report, the user enters the cycle day, energy level, symptom IDs, mood IDs, and optional notes. The program determines the menstrual phase using a fixed array and detects a condition using symptom-selection rules.

Food recommendations are stored in an unordered map where each condition maps to a vector of `FoodInfo` objects. Matching foods are inserted into a priority queue so that higher-priority recommendations are displayed first.

Yoga poses and breathing exercises are stored in vectors and filtered according to user input. Cycle transitions are stored using an ordered map, forming a logical directed cyclic graph.

Health reports are stored in a vector for the duration of the program session. A redo stack is declared for history-management design, although complete undo/redo commands are not currently implemented.

## 4. Data Structures Utilized

The project uses the following data structures:

- **Arrays** for fixed-size cycle-phase, symptom, and mood data.
- **Vectors** for dynamically sized collections such as symptoms, moods, health history, yoga poses, breathing exercises, and food lists.
- **Priority Queue** for ranking food recommendations.
- **Binary Heap** as the underlying structure of the C++ priority queue.
- **Ordered Map (`std::map`)** for menstrual-cycle transitions.
- **Unordered Map (`std::unordered_map`)** as a hash table for fast condition-to-food lookup.
- **Set (`std::set`)** for unique categories and symptom membership checks.
- **Stack (`std::stack`)** for redo-related history storage.
- **Directed cyclic graph model** for phase transitions.
- **User-defined structs** for grouping related domain information.

More detail is available in `docs/data-structures.md`.

## 5. Results and Conclusion

The project successfully demonstrates the practical application of multiple Data Structures in a single C++ console application. Users can record health information, identify their menstrual-cycle phase, receive prioritized nutrition recommendations, view yoga poses and breathing exercises, and inspect health history from the current session.

As an Experiential Learning Project, the main outcome is the practical understanding of how different data structures are selected according to the problem being solved. Arrays support direct indexed access, vectors provide dynamic storage, hashing supports fast lookup, priority queues support prioritization, and maps can be used to represent relationships between cycle phases.

The application can be extended in the future with persistent storage, variable cycle lengths, user accounts, a graphical interface, cycle prediction, analytics, and complete undo/redo functionality.
