# ⚽ SportMatrix — AI-Powered Football Player Selection System

![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python)
![Flask](https://img.shields.io/badge/Flask-2.x-black?logo=flask)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-ML-orange?logo=scikit-learn)
![License](https://img.shields.io/badge/License-MIT-green)

> A data-driven football analytics platform that uses **TOPSIS + Decision Tree** hybrid ranking to evaluate players and recommend the best team lineup.
3rd Semester College Project



---

## 📌 Overview

**SportMatrix** is a web-based sports analytics system built with Flask that helps coaches and analysts make smarter decisions. Players are entered via position-specific forms (Attacker, Midfielder, Defender, Goalkeeper), and the system applies a **hybrid ML model** to rank them and suggest an optimal starting XI.

---

## ✨ Features

- 🧠 **Hybrid AI Ranking** — Combines TOPSIS multi-criteria scoring with a Decision Tree Regressor for final player selection
- 📋 **Position-Based Forms** — Separate data entry forms for ATC, MID, DEF, and GK roles
- 📊 **Performance Visualization** — Scatter plots showing each player's predicted vs. actual performance score
- 🏆 **Auto Team Lineup** — Picks the best 3 ATCs, 3 MIDs, 4 DEFs, 2 GKs from registered players
- 🔁 **Substitute Ranking** — All non-selected players are ranked as substitutes
- 📈 **Stat Analysis** — Each player submission is compared against position-specific thresholds (good/low per attribute)
- 🗃️ **Excel Storage** — Player data is persisted in `data.xlsx` using `openpyxl`

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML, CSS, JavaScript, Chart.js |
| Backend | Python, Flask |
| Data Processing | Pandas, NumPy |
| Machine Learning | scikit-learn (Decision Tree Regressor) |
| Ranking Algorithm | TOPSIS (Min-Max Normalized, Weighted) |
| Visualization | Matplotlib |
| Storage | Excel (openpyxl) |

---

## 🗂️ Project Structure

```
SportMatrix/
├── app.py                  # Main Flask application & ML logic
├── data.xlsx               # Player database (auto-created on first run)
├── Sportmatrix.gitignore   # Git ignore rules
├── templates/
│   ├── sportmatrix1.html   # Home page
│   ├── sportmatrix2.html   # Add player page
│   ├── sportmatrixATC.html # Attacker form
│   ├── sportmatrixMID.html # Midfielder form
│   ├── sportmatrixDEF.html # Defender form
│   ├── sportmatrixGK.html  # Goalkeeper form
│   ├── sportmatrixTEAM.html# Team lineup & scatter plot
│   └── sportmatrixFIN.html # Player analysis result
└── static/
    └── ...                 # CSS, JS, images
```

---

## 🚀 Getting Started

### Prerequisites
- Python 3.8 or higher
- pip

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/SportMatrix.git
   cd SportMatrix
   ```

2. **(Recommended) Create a virtual environment**
   ```bash
   python -m venv sportmatrix_env
   # Windows
   sportmatrix_env\Scripts\activate
   # macOS/Linux
   source sportmatrix_env/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install flask pandas numpy matplotlib scikit-learn openpyxl
   ```

4. **Run the app**
   ```bash
   python app.py
   ```

5. **Open in browser**
   ```
   http://127.0.0.1:5000
   ```

---

## 📊 How It Works

```
Player Data Entry (Form)
        ↓
  Excel Storage (data.xlsx)
        ↓
  Preprocessing (BMI + Avg Performance Score)
        ↓
  TOPSIS Ranking (Weighted Multi-Criteria)
        ↓
  Decision Tree Regressor (Predicted Selection Score)
        ↓
  Hybrid Score = 50% TOPSIS + 50% Decision Tree
        ↓
  Top Players Selected by Position → Team Lineup
```

### Position Thresholds

| Stat | ATC | MID | DEF | GK |
|---|---|---|---|---|
| Passing | 85 | 90 | 75 | 70 |
| Shooting | 95 | 85 | 60 | 80 |
| Dribbling | 95 | 80 | 70 | 45 |
| Pace | 90 | 75 | 85 | 50 |
| Physical | 50 | 50 | 75 | 75 |
| Defending | 40 | 70 | 95 | 95 |

---

## 👤 Author

**Utkarsh Mishra**  
GitHub: [@Utkarsh7106](https://github.com/Utkarsh7106)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

> 🎓 Built as a 5th Semester college project — exploring the intersection of sports analytics and machine learning.
