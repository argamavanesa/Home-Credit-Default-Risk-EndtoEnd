# Home-Credit-Default-Risk-EndtoEnd

Proyek ini berisi pipeline end-to-end untuk prediksi default kredit pada dataset Home Credit Default Risk.

## Gambaran Umum

Alur kerja di notebook:

1. Load 7 tabel mentah dari folder `data/`.
2. Agregasi tabel riwayat ke level `SK_ID_CURR`.
3. Join semua tabel menjadi master dataset.
4. Data wrangling: perbaikan anomali, feature engineering, dan pembuangan kolom dengan missing value tinggi.
5. EDA untuk melihat distribusi target, fitur numerik, missing value, dan pola kategori.
6. Encoding kategorikal dan imputasi nilai hilang.
7. Feature selection.
8. Split train/test, handling imbalance dengan SMOTE.
9. Training model: Logistic Regression, Random Forest, Gradient Boosting, XGBoost, LightGBM, dan Voting Ensemble.
10. Evaluasi model dengan metrik klasifikasi, confusion matrix, ROC curve, PR curve, dan cross-validation.

## Struktur Folder

```
home_credit_project/
├── home_credit_notebook.ipynb
├── README.md
├── requirements.txt
├── HomeCredit_columns_description.csv
├── data/
│   ├── application_train.csv
│   ├── application_test.csv
│   ├── bureau.csv
│   ├── bureau_balance.csv
│   ├── previous_application.csv
│   ├── POS_CASH_balance.csv
│   ├── credit_card_balance.csv
│   ├── installments_payments.csv
│   └── sample_submission.csv
└── outputs/
    ├── figures/
    ├── models/
    ├── master_dataset.parquet
    ├── model_metrics_test.csv
    └── model_cv_scores.csv
```

## Cara Menjalankan

1. Install dependency:
   ```bash
   pip install -r requirements.txt
   ```

2. Pastikan semua file CSV Kaggle sudah ada di folder `data/`.

3. Buka dan jalankan [home_credit_notebook.ipynb](home_credit_notebook.ipynb) secara berurutan dari atas ke bawah.

4. Jika ingin menjalankan lebih cepat untuk percobaan awal, aktifkan mode dev di bagian konfigurasi notebook.

## Output

Hasil utama disimpan di folder `outputs/`, terutama:

- `outputs/figures/` untuk visualisasi EDA dan evaluasi
- `outputs/model_metrics_test.csv` untuk metrik test set
- `outputs/model_cv_scores.csv` untuk hasil cross-validation
- `outputs/master_dataset.parquet` untuk dataset gabungan hasil join
