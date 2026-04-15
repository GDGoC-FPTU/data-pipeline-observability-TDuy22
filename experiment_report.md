# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600267
**Name:** Pham Thanh Duy
**Date:** 2026-04-15

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | Hop ly voi tap du lieu da duoc validate va loai bo gia tri bat thuong/khong hop le. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Sai nghiem trong vi model bi outlier chi phoi, khong co co che robust de loai bo ban ghi doc. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Khi dung garbage data, agent khong con thay duoc "chat luong su that" cua thong tin ma chi thay so lon nhat trong cot gia. Ban ghi "Nuclear Reactor" co gia 999999 la outlier, nhung logic truy van hien tai lai lay san pham electronics co gia cao nhat, nen ket qua bi lech hoan toan. Ngoai ra bo du lieu rac con co duplicate ID, null values va sai kieu du lieu ("ten dollars"), cac loi nay lam giam do tin cay cua toan bo bang du lieu. Neu pipeline khong validate tu dau vao, chi can mot vai ban ghi xau da du de agent dua ra khuyen nghi sai, gay rui ro cho quyet dinh kinh doanh.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** (Dong y hay khong? Giai thich ngan gon.)

Dong y. Prompt tot chi giup dat cau hoi ro rang, nhung neu du lieu dau vao bi ban thi output van sai. Trong bai nay, cung mot cau hoi nhung ket qua khac nhau ro ret giua clean data va garbage data. Vi vay, dat chat luong du lieu va cac buoc observability (validate, logging, timestamp) la dieu kien bat buoc truoc khi toi uu prompt.
