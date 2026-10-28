# India-Stocks-1711-1740-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 1711 to 1740)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-1711-1740-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (1711 to 1740)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 1711 | `ICICILIFE` | ICICI Life Insurance Ltd. | `ICICILIFE.NS` |
| 1712 | `BONDADA` | Bondada Engineering Limited | `BONDADA.NS` |
| 1713 | `BONFIG` | Bonfiglioli Transmissions Limited | `BONFIG.NS` |
| 1714 | `FUSIONCX` | Fusion CX Limited | `FUSIONCX.NS` |
| 1715 | `JPL` | Jio Platforms Limited | `JPL.NS` |
| 1716 | `KHAZANCHI` | Khazanchi Jewellers Limited | `KHAZANCHI.NS` |
| 1717 | `MUTHOOTCAP` | Muthoot Capital Services Limited | `MUTHOOTCAP.NS` |
| 1718 | `MUTHOOTMF` | Muthoot Microfin Limited | `MUTHOOTMF.NS` |
| 1719 | `MVELECTRO` | MV Electrosystems Limited | `MVELECTRO.NS` |
| 1720 | `MVGJL` | Manoj Vaibhav Gems N Jewellers Limited | `MVGJL.NS` |
| 1721 | `MWL` | Mangalam Worldwide Limited | `MWL.NS` |
| 1722 | `MYSORPETRO` | Mysore Petro Chemicals Limited | `MYSORPETRO.NS` |
| 1723 | `NACLIND` | NACL Industries Limited | `NACLIND.NS` |
| 1724 | `NAGREEKCAP` | Nagreeka Capital & Infrastructure Limited | `NAGREEKCAP.NS` |
| 1725 | `NAGREEKEXP` | Nagreeka Exports Limited | `NAGREEKEXP.NS` |
| 1726 | `NAHARCAP` | Nahar Capital and Financial Services Limited | `NAHARCAP.NS` |
| 1727 | `NAHARINDUS` | Nahar Industrial Enterprises Limited | `NAHARINDUS.NS` |
| 1728 | `NAHARPOLY` | Nahar Poly Films Limited | `NAHARPOLY.NS` |
| 1729 | `NAHARSPING` | Nahar Spinning Mills Limited | `NAHARSPING.NS` |
| 1730 | `NARMADA` | Narmada Agrobase Limited | `NARMADA.NS` |
| 1731 | `NATCAPSUQ` | Natural Capsules Limited | `NATCAPSUQ.NS` |
| 1732 | `NATHBIOGEN` | Nath Bio-Genes (India) Limited | `NATHBIOGEN.NS` |
| 1733 | `NATIONSTD` | National Standard (India) Limited | `NATIONSTD.NS` |
| 1734 | `NAVKARCORP` | Navkar Corporation Limited | `NAVKARCORP.NS` |
| 1735 | `NAVKARURB` | Navkar Urbanstructure Limited | `NAVKARURB.NS` |
| 1736 | `NAVNETEDUL` | Navneet Education Limited | `NAVNETEDUL.NS` |
| 1737 | `NAZARA` | Nazara Technologies Limited | `NAZARA.NS` |
| 1738 | `NBIFIN` | N. B. I. Industrial Finance Company Limited | `NBIFIN.NS` |
| 1739 | `NCLIND` | NCL Industries Limited | `NCLIND.NS` |
| 1740 | `NDGL` | Naga Dhunseri Group Limited | `NDGL.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream ICICILIFE 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-1711-1740-Historical-Data/main/ICICILIFE/1m/2026/10/ICICILIFE_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
