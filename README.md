[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23574158&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** phamthanhduyvbhp@gmail.com
**Name:** Phạm Thành Duy
**Student ID:** 2A202600267

---

## Mo ta

Day la bai lab ETL co bo sung observability de kiem soat chat luong du lieu dau vao. Trong bai lam nay, toi da hoan thanh day du 4 buoc `extract`, `validate`, `transform`, `load` trong `solution.py`. Pipeline doc du lieu JSON, loai bo ban ghi khong hop le (`price <= 0`, `category` rong), tinh cot `discounted_price`, chuan hoa `category` theo Title Case, gan cot `processed_at`, sau do luu ket qua ra `processed_data.csv`.

Ngoai ra, toi da thuc hien stress test bang cach so sanh agent response giua clean data va garbage data, tu do danh gia tac dong cua data quality den ket qua suy luan.

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
python generate_garbage.py
python agent_simulation.py
```

Lenh tren se tao `garbage_data.csv` va in ket qua so sanh giua `processed_data.csv` (clean) va `garbage_data.csv` (poisoned).

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

- ETL da doc 5 records tu `raw_data.json`.
- Validation giu lai 3 records hop le, loai 2 records loi.
- Output `processed_data.csv` duoc tao thanh cong va co them `discounted_price`, `processed_at`.
- Trong stress test:
	- Clean Data: agent tra loi hop ly (`Laptop at $1200`).
	- Garbage Data: agent bi outlier chi phoi (`Nuclear Reactor at $999999`).

Dieu nay cho thay data quality anh huong truc tiep den do chinh xac cua he thong AI.
