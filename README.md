# LRU Cache Implementation with JavaScript

## 🛠️ Data Structures Used & Why

This solution uses JavaScript's native **`Map`** (or a **Doubly Linked List + HashMap**):

1. **HashMap (`Map`):** Allows key lookups in $O(1)$ time to quickly retrieve stored values without scanning the entire structure.
2. **Doubly Linked List / Insertion-Ordered Map:** Keeps track of access history:
   - **Most Recently Used (MRU):** Positioned at the top/end of the order.
   - **Least Recently Used (LRU):** Positioned at the bottom/start for instant $O(1)$ eviction.

Using an array alone would require $O(N)$ time to search and shift elements. Combining a hash map with linked node ordering guarantees $O(1)$ operations.

## 🔄 How LRU Ordering is Maintained

- **`get(key)`**: Accessing an existing key retrieves its value and updates its status as the Most Recently Used (MRU).
- **`put(key, value)`**: 
  - If the key exists, its value is updated and moved to the MRU position.
  - If the key is new and capacity is exceeded, the Least Recently Used (LRU) item is removed before inserting the new key-value pair at the MRU position.

## ⏱️ Complexity Analysis

| Operation | Time Complexity | Space Complexity |
| :--- | :--- | :--- |
| `get(key)` | $O(1)$ | $O(1)$ |
| `put(key, value)` | $O(1)$ | $O(1)$ |
| **Overall Cache Space** | — | $O(C)$ where $C$ is the capacity |

## 🚀 How to Run

### Prerequisites
- [Node.js](https://nodejs.org/) (v14 or higher recommended)

### Instructions
1. Use `node lru.js` in your terminal