# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-9999
**Name:** Bap Non Vo Dich
**Date:** 2026-06-10

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 10 | Agent chon dung san pham voi muc gia hop le. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Phone at $abc. | 1 | Agent tra ve gia tri string "abc" do loi du lieu dau vao chua duoc kiem tra. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Khi Agent truy xuat vao tap `garbage_data.csv`, tap nay chua cac gia tri "rac" nhu cot `price` chua string (vi du "abc") hoac so am, cung nhu viec thieu thong tin category. Do chung ta su dung ham `idxmax()` cua pandas tren cot `price` ma khong validation tu dau, pandas co the hieu nham day la chuoi string hoac ra ket qua vo ly. Tu do, Agent lay "Phone" voi gia "$abc" lam ket qua "best deal", mot dieu hoan toan vo ly voi nguoi dung. Data chat luong kem da gay "o nhiem" kien thuc cua Agent va khien toan bo he thong RAG tro nen thieu tin cay (Garbage In, Garbage Out).

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y.

Cho du prompt co xuat sac den dau, neu du lieu cho AI xu ly (RAG) bi sai lech hoac co kieu du lieu khong hop le, ket qua sinh ra se luon bi sai (hallucination). Chat luong cua data la yeu to tien quyet nhat de AI hoat dong dung ky vong va giam thieu rui ro (nhu tu van gia tien bang string "abc" hoac so am cho khach hang).
