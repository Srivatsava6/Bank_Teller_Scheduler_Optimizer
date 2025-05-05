# 🏦 Bank Teller Scheduling Optimizer

## 👥 Team Members:
- Srivatsava Chinnasamy Kamaraj  srivatsava.chinnasamykamaraj.24@neoma-bs.com
- Manibalan Amaranathan  manibalan.amarnathan.24@neoma-bs.com

---

## 🙏 Acknowledgment

We used **ChatGPT by OpenAI** to assist in reviewing and formatting our algorithm, clarifying Python syntax, and ensuring modular design.  
> 🧠 **However, the core logic, constraints, and pruning approach are fully original and uniquely developed by me(Srivatsava)** based on our understanding of the problem. Same question given to chatgpt will give you different ouput and combinations.

## 📘 Project Overview

This project is inspired by a classic **linear programming problem** from:

> Heizer, J., Render, B., & Munson, C. (2020). *Operations Management: Sustainability and Supply Chain Management* (12th ed., Chapter 8). Harlow: Pearson Education.

The specific problem comes from the **Hong Kong Bank of Commerce and Industry** case study (Table 8.4), where the goal is to **minimize staffing costs** while meeting teller demand throughout the day.

---

## 🧠 Methodology

Instead of using mathematical solvers, we built a **brute-force algorithm** combined with a **custom pruning strategy** that intelligently eliminates invalid or suboptimal combinations early. This lets us explore a large solution space **efficiently using only core Python** (loops, conditionals, dictionaries).

While more optimal approaches (e.g., LP solvers) exist, our implementation emphasizes:
- Deep understanding of the underlying logic  
- Use of only Python structures taught in class  
- Thoughtful constraints to cut down unnecessary computation

---

## 📌 Problem Description

- Bank requires **10–18 tellers per hour**, depending on the time.
- **Full-time tellers** work from **9 AM to 5 PM**, with a **1-hour lunch break** staggered between 12–2 PM.
- **Part-time tellers**:
  - Work exactly **4 consecutive hours**
  - Can start between **9 AM and 1 PM**
  - Are **less expensive** than full-timers
- Maximum part-time hours allowed = **50% of total daily demand**
- Goal: **Minimize total cost** while meeting hourly demand

---

## 💡 Constraints Implemented

- Each full-timer costs **$100/day**
- Each part-timer costs **$8/hour = $32/day**
- No more than 50% of total staffing can be part-time hours
- A maximum number of part-timers are calculated based on demand
- Part-timer shift start times range from **9 AM to 1 PM**

---

## 🧮 Example Demand Input used

Hour 9:00 - 10:00 → 10
Hour 10:00 - 11:00 → 12
Hour 11:00 - 12:00 → 14
Hour 12:00 - 13:00 → 16
Hour 13:00 - 14:00 → 18
Hour 14:00 - 15:00 → 17
Hour 15:00 - 16:00 → 15
Hour 16:00 - 17:00 → 10

## 📤 Output Includes

- ✅ Best staffing schedule
- 💰 Total cost of staffing
- 🧍‍♂️ Number of full-time tellers used
- 🕒 Shift-wise assignment of part-time tellers
- 📊 Hour-by-hour breakdown of teller coverage
