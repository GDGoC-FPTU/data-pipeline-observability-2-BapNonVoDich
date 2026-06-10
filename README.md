[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=24112722&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** email@example.com
**Name:** Bap Non Vo Dich

---

## Mo ta

Da hoan thanh viet script `solution.py` cho ETL pipeline (bao gom Extract file JSON, Validate gia va danh muc, Transform gia giam 10% va chuan hoa danh muc, Load vao file CSV). Da chay thu mo phong RAG agent cho thay du lieu "rac" se khien agent dua ra cau tra loi vo ly hoac gap loi he thong.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
# De chay simulation voi Clean data (processed_data.csv) va Garbage data (garbage_data.csv), chay lenh:
python agent_simulation.py
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

Da doc tong cong 5 records tu `raw_data.json`.
Sau qua trinh Validate, 2 records bi loai (do price am/bang 0 hoac category rong).
Pipeline da transform va luu thanh cong 3 records hop le vao `processed_data.csv`.
Agent Simulation hoat dong on dinh voi `processed_data.csv` va hoat dong sai lech hoan toan voi `garbage_data.csv` (Agent dua ra san pham Phone voi muc gia $abc).
