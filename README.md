<img width="1368" height="640" alt="image" src="https://github.com/user-attachments/assets/4b10cd58-1bfe-4d3d-8d32-5f874de5c5a9" /># GigiQuant — Quantitative Financial Analysis in C

GigiQuant is a comprehensive C project designed to analyze stock market data and model financial scenarios using various data structures and algorithms. The project is structured as a series of tasks for a quantitative portfolio manager role [cite: 4]>>, solving real-world financial problems ranging from basic risk assessment to probability modeling using Markov Chains[cite: 5].

You can find the full source code on GitHub: https://github.com/inwhapp-arch/Project_PA_2026

---

## 📌 Project Overview & Structure

>>The codebase is split into four main standalone programs, each tackling a specific financial concept and utilizing different data structures (linked lists, stacks, queues, binary trees, and graphs)[cite: 5]. 

### Task 1: Portfolio Performance & Sharpe Ratio
**File:** `task1.c` (or your specific filename)

>>This module evaluates how "profitable" the assumed risk of a portfolio was by calculating the Sharpe Ratio[cite: 12].
* **How it works:** The program prompts the user via standard input to enter the number of days and the daily portfolio values.
* >>**Data Structure:** It dynamically builds a singly linked list to store the daily values and calculate the daily returns[cite: 66, 67].
* >>**Math:** It computes the average return, the portfolio volatility (standard deviation), and finally the Sharpe Ratio (assuming a risk-free rate of 0)[cite: 64]. 
* **Output:** The result is printed directly to the console.

### Task 2: Market Arbitrage Detection
**File:** `task2.c` (or your specific filename)

>>This task identifies risk-free profit opportunities (arbitrage) by finding instances where the same asset is priced differently across three major European markets: London, Berlin, and Paris[cite: 105, 106].
* >>**How it works:** It reads chronological price data from a hardcoded file named `markets.txt`[cite: 123].
* >>**Data Structure:** The program uses three linked-list-based stacks to store the prices for each city[cite: 128]. It evaluates the prices simultaneously. >>If exactly two markets have the same price and the third is different, an arbitrage opportunity is flagged[cite: 114].
* >>**Output:** The opportunities are stored in a custom Queue and then exported to an `output.txt` file, logging the day, the absolute price difference, and the outlier market[cite: 126, 128].

### Task 3: Portfolio Diversification via Binary Trees
**File:** `task3.c` (or your specific filename)

>>To stabilize a portfolio, this module finds pairs of highly volatile stocks that move in perfectly opposite directions (sister stocks)[cite: 166, 208]. 
* **How it works:** It takes the number of assets, number of days, asset names, and their daily prices via standard input.
* **Data Structure:** It constructs a dynamic Binary Tree. >>For each day, if a stock's price drops, it moves to the `left` child; if it rises, it moves to the `right` child[cite: 168]. 
* **Output:** By recording the path of each stock, the program cross-references them to find pairs that mirror each other completely. These pairs are printed to the console (e.g., `AAPL--AMZN`).

### Task 4: Markov Chain Price Predictor
**File:** `task4.c` (or your specific filename)

>>This module models stock price behaviors using Markov Chains to determine the probability of a stock reaching a specific target price over a given number of days[cite: 5, 251, 284].
* >>**How it works:** It reads initial parameters (historical prices, interval size, simulation days, start price, and target price) from a local `data.txt` file[cite: 275, 276, 277, 278, 279, 280].
* >>**Data Structure:** It groups prices into discrete intervals (states) and builds a transition matrix representing a directed graph[cite: 253, 254, 256].
* >>**Math:** To prevent floating-point precision loss over multiple days, probabilities are calculated using exact fractional arithmetic (numerators and denominators), simplified at each step using the Greatest Common Divisor (GCD)[cite: 285].
* >>**Output:** The daily probability of hitting the target price is printed to the console as an irreducible fraction (e.g., `1/3`, `4/9`)[cite: 285, 312, 313].

---

## 🚀 How to Run

Because the project is split into distinct logical units, you need to compile and run each task separately using a standard C compiler (like `gcc`).
**Example for Task 2 (Arbitrage):**
```bash
# Compile the code
gcc task2.c -o arbitrage

# Ensure markets.txt is in the same directory, then run
./arbitrage

```
🤝 Contributing
Contributions, issues, and feature requests are welcome!

Fork the repository 2. Create a new branch (git checkout -b feature/improvement)

Commit your changes (git commit -m 'Add some feature')

Push to the branch (git push origin feature/improvement)

Open a Pull Request

Check the Issues page if you want to report a bug or discuss future additions.
