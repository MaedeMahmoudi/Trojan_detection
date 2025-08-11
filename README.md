
# Trojan Detection (Verilog + Machine Learning)

پروژه‌ای برای تشخیص **تروجان سخت‌افزاری** در مدارهای دیجیتال با استفاده از شبیه‌سازی Verilog و مدل‌های یادگیری ماشین.  

---

## 📂 ساختار پروژه
```

trojan-detection/
├── README.md
├── LICENSE
├── .gitignore
├── requirements.txt
├── src/
│   ├── verilog/        # کدهای Verilog (clean و trojan)
│   ├── sim/            # تست‌بنچ‌ها و اسکریپت‌های شبیه‌سازی
│   └── py/             # اسکریپت‌های پایتون (پردازش و آموزش مدل)
├── data/
│   ├── raw/            # داده خام (VCD و ...)
│   ├── external/       # دیتاست Trust-HUB
│   └── processed/      # داده پردازش‌شده
├── experiments/        # پیکربندی و نتایج آزمایش‌ها
├── models/             # مدل‌های ذخیره‌شده
├── results/            # خروجی‌ها و گراف‌ها
└── docs/               # مستندات و دیاگرام‌ها

````

---

## ⚙️ پیش‌نیازها
- **سیستم‌عامل:** Arch Linux یا سایر لینوکس‌ها  
- **ابزارهای Verilog:** iverilog, vvp, gtkwave  
- **پایتون:** نسخه 3.10 یا بالاتر  
- **پکیج‌ها:** در فایل `requirements.txt`  

---

## 🚀 نصب و راه‌اندازی سریع
```bash
# ساخت محیط مجازی
python -m venv .venv
source .venv/bin/activate

# نصب پکیج‌ها
pip install -r requirements.txt
````

---

## 🖥 اجرای شبیه‌سازی نمونه

```bash
# اجرای تست‌بنچ ساده
iverilog -o simv src/verilog/clean/example.v src/sim/tb_smoke.v
vvp simv
```

---

## 📊 استخراج ویژگی و آموزش مدل

```bash
# استخراج ویژگی از VCD
python src/py/extract_features.py --input data/raw --output data/processed/features.csv

# آموزش مدل
python src/py/train.py --config experiments/exp_001/config.yaml
```

---

## 📥 اضافه کردن دیتاست Trust-HUB

```bash
git submodule add https://github.com/trust-hub/Trust-HUB.git data/external/Trust-HUB
git submodule update --init --recursive
```

---


