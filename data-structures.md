# Data Structures Used

This document explains the data structures used in the Menstrual Health Tracker and where they appear in the code.

## 1. Arrays

Three fixed-size C++ arrays are used:

```cpp
string cyclePhaseArray[28];
string symptomMenu[20];
string moodMenu[15];
```

`cyclePhaseArray` provides direct phase lookup by cycle day. `symptomMenu` and `moodMenu` provide ID-to-name mapping for fixed menus.

## 2. Vectors

Vectors are used in several places:

```cpp
vector<int> symptoms;
vector<int> moods;
vector<HealthEntry> historyStack;
vector<YogaAsana> yogaDatabase;
vector<BreathingExercise> breathingDatabase;
```

Vectors also appear as the value type inside the food hash table:

```cpp
unordered_map<string, vector<FoodInfo>> foodHashTable;
```

They are appropriate because these collections are dynamically sized and traversed sequentially.

## 3. Priority Queue

Food recommendations are ranked using:

```cpp
priority_queue<FoodInfo, vector<FoodInfo>, CompareFoodPriority> pq;
```

The custom comparator ensures that foods with a higher `priority` value are returned first.

## 4. Binary Heap

The project does not manually declare a heap class. Instead, the C++ `priority_queue` uses heap operations internally on its underlying container. Therefore, the project directly uses a **priority queue** and indirectly uses a **binary heap** implementation concept.

## 5. Ordered Map

Cycle phase transitions are stored using:

```cpp
map<string, string> cycleGraph;
```

`std::map` keeps keys ordered and typically provides logarithmic search, insertion, and deletion.

## 6. Graph Model

The entries in `cycleGraph` logically model this directed cycle:

```text
Menstrual → Follicular → Ovulation → Luteal → Menstrual
```

The vertices are the menstrual phases and each map entry describes the directed edge to the next phase.

This is a logical graph representation using a map, rather than a general-purpose graph class.

## 7. Unordered Map / Hash Table

Food data is stored in:

```cpp
unordered_map<string, vector<FoodInfo>> foodHashTable;
```

The key is a condition name and the value is a vector of food recommendations. This supports efficient average-case lookup by condition.

## 8. Set

Global sets store unique categories:

```cpp
set<string> symptomCategories;
set<string> conditionCategories;
```

A local set is also created in condition detection:

```cpp
set<int> symptomSet(symptoms.begin(), symptoms.end());
```

This makes membership checks such as `symptomSet.count(0)` convenient.

## 9. Stack

A stack is declared as:

```cpp
stack<HealthEntry> redoStack;
```

It is intended for redo-related history management. In the current implementation it is cleared after a new health entry is saved, but no user-facing undo/redo commands are implemented.

## 10. Structs

The following user-defined structures group related information:

```text
FoodInfo
YogaAsana
BreathingExercise
HealthEntry
CompareFoodPriority
```

`CompareFoodPriority` is technically a comparator struct rather than a data record, and it controls priority-queue ordering.

## 11. Strings and String Stream

`std::string` is used throughout the program for names, descriptions, commands, dates, phases, conditions, and notes.

`std::stringstream` is used when formatting the current date for a health entry.

## 12. Time Structures

The standard library time types `time_t` and `tm` are used to obtain the current local date for the report.

## Not Used

A linked list is not explicitly used in the project. There is no custom pointer-based linked-list implementation and neither `std::list` nor `std::forward_list` is used.
