# BIST 100 Hisse Yönü ve Portföy Trend Tahmini

BIST 100 içinden seçilen 10 hisse ve XU100 endeksinin **2021–2025 haftalık** verileriyle gelecek hafta yön tahmini (`Target_1W`), olasılık tabanlı portföy trend skoru ve 2025 yılı backtest analizi.

## Proje Kapsamı
- **Veri:** 10 BIST 100 hissesi (`THYAO.IS`, `TUPRS.IS`, `ASELS.IS`, `BIMAS.IS`, `AKBNK.IS`, `GARAN.IS`, `KCHOL.IS`, `SAHOL.IS`, `EREGL.IS`, `TCELL.IS`) + `XU100.IS` (2021–2025, `interval='1wk'`, `auto_adjust=True`).
- **Eğitim / Test:** Mayıs 2021 – Aralık 2024 (`1.900` satır) Eğitim · 2025 (`510` satır, 51 hafta) Test.
- **Modeller:** Logistic Regression (Referans) ve Random Forest (Ana Model).

## Klasör Yapısı
- `data/raw/` — Ham haftalık OHLCV verileri (`bist10_raw.csv`, `xu100_raw.csv`)
- `data/processed/` — Temizlenmiş ve 11 teknik özellik eklenmiş veri (`bist10_features.csv`)
- `notebooks/` — Faz 1 (`01_veri_hazirlama_semih.ipynb`), Faz 2 (`02_modelleme_seha.ipynb`), Faz 3 (`03_karsilastirma_portfoy_samet.ipynb`)
- `outputs/` — Model tahminleri, metrikler ve `dpi=300` grafikler

## Kurulum
```bash
pip install -r requirements.txt
```

## Ekip
- **Semih:** Veri Toplama, Temizleme ve Özellik Mühendisliği
- **Seha:** Modelleme ve Olasılık Üretimi
- **Samet:** Model Karşılaştırma, Portföy Trend Skoru ve Backtest