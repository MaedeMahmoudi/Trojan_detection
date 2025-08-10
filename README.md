```markdown
# Trojan-Detection (Verilog + ML)

پروژه‌ای برای شناسایی تروجان در مدارهای دیجیتال با استفاده از شبیه‌سازی Verilog و مدل‌های یادگیری ماشین.

## ساختار پروژه
```

trojan-detection/
├── README.md
├── LICENSE
├── .gitignore
├── Makefile
├── requirements.txt
├── notebooks/
├── src/
│   ├── verilog/
│   │   ├── clean/
│   │   ├── trojan/
│   │   └── common/
│   ├── sim/
│   └── py/
├── data/
│   ├── raw/
│   ├── external/
│   └── processed/
├── experiments/
├── models/
├── results/
├── tools/
├── docs/
└── .github/

````

## پیش‌نیازها
- Arch Linux یا هر توزیع لینوکس
- iverilog, vvp, gtkwave
- Python 3.10+
- پکیج‌های پایتون موجود در `requirements.txt`

## نصب سریع
```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
````

## اجرای نمونه شبیه‌سازی

```bash
make sim-smoke
```

یا:

```bash
iverilog -o simv src/verilog/clean/example.v src/sim/tb_smoke.v
vvp simv
```

## استخراج ویژگی و آموزش مدل

```bash
make extract-features
python src/py/train.py --config experiments/exp_001/config.yaml
```

## اضافه کردن Trust-HUB

```bash
git submodule add https://github.com/trust-hub/Trust-HUB.git data/external/Trust-HUB
git submodule update --init --recursive
```

## قوانین و نکات

* شاخه‌بندی: main, dev, feature/<name>
* پیام کامیت طبق Conventional Commits
* استفاده از Git LFS برای فایل‌های بزرگ

```

