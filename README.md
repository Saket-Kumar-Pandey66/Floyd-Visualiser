# 🐢🐇 Floyd's Cycle Detection Visualiser

An **interactive visualiser** for **Floyd’s Cycle Detection Algorithm**, also known as the **Tortoise and Hare Algorithm**.  
This project helps you *see how the algorithm works step-by-step* in detecting cycles in a linked list.

---

## 🧠 About the Project

Floyd’s Algorithm uses two pointers — one slow (🐢) and one fast (🐇).  
The slow pointer moves one step at a time, and the fast pointer moves two.  
If there’s a cycle, they eventually meet; if not, the fast pointer reaches the end.

This visualiser lets you:
- Add or remove nodes dynamically
- Create or remove cycles
- Step through each phase of the algorithm
- Watch the tortoise 🐢 and hare 🐇 move live
- Learn visually how cycle detection works

---

## ✨ Features

✅ Interactive linked list builder  
✅ Step-by-step simulation  
✅ Color-coded pointers (🐢 = slow, 🐇 = fast, 💜 = meet point)  
✅ Cycle start detection highlighting  
✅ Clean, responsive user interface  
✅ View original C implementation inside the app  

---

## 🧩 Technologies Used

| Technology | Purpose |
|-------------|----------|
| **HTML5** | Page structure |
| **CSS3** | Styling and layout |
| **JavaScript (Vanilla)** | Algorithm logic and animation |
| **GitHub Pages** | Free hosting for live demo |

---

## 🧮 Algorithm (C Code Example)

```c
struct Node* detectCycle(struct Node* head) {
    struct Node* slow = head;
    struct Node* fast = head;
    
    while (fast != NULL && fast->next != NULL) {
        slow = slow->next;
        fast = fast->next->next;
        
        if (slow == fast) break;
    }
    
    if (fast == NULL || fast->next == NULL)
        return NULL;
    
    slow = head;
    while (slow != fast) {
        slow = slow->next;
        fast = fast->next;
    }
    
    return slow;
}
