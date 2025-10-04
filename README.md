# Telekom-musteri-churn-analizi
Müşteri verilerinden churn tahmini ve iyileştirme stratejileri geliştirme.
# 📊 Telco Customer Churn Analizi

## 🎯 Proje Amacı
Bu proje, Kaggle üzerinde bulunan [Telco Customer Churn Dataset](https://www.kaggle.com/datasets/blastchar/telco-customer-churn) kullanılarak gerçekleştirilmiştir.  
Amaç, **müşteri kaybını (churn) tahmin etmek**, riskli müşteri gruplarını belirlemek ve iş açısından uygulanabilir stratejiler önermektir.  

---

## 📂 Proje Yapısı
- **01_data_exploration.ipynb** → Veri yükleme, temizlik, ilk keşifsel analizler (EDA).  
- **02_visual_analysis.ipynb** → Churn dağılımları, sözleşme türü, internet servisi, tenure analizleri.  
- **03_modeling.ipynb** → Logistic Regression, Random Forest ve XGBoost ile modelleme.  
- **04_feature_importance.ipynb** → Özellik önemleri ve iş açısından yorumlar.  
- **README.md** → Proje özeti ve raporu.  

---

## 🔍 Keşifsel Analiz (EDA) Bulguları
- **Sözleşme Süresi:** Aylık kontratlı müşterilerde churn oranı yüksek.  
- **İnternet Servisi:** Fiber internet kullanıcılarında churn oranı DSL’e göre daha fazla.  
- **Ek Hizmetler:** OnlineSecurity ve TechSupport hizmeti almayan müşteriler daha çok ayrılıyor.  
- **Müşteri Kıdemi:** İlk yıl (0–12 ay) churn riski en yüksek.  
- **Ödeme Yöntemi:** Elektronik çek ile ödeme yapanlarda churn daha fazla.  

---

## 🤖 Modelleme Sonuçları
Üç farklı model denendi:

| Model | Accuracy | ROC-AUC | Recall (Churn=1) | Not |
|-------|----------|---------|------------------|-----|
| Logistic Regression | 0.80 | 0.842 | 0.53 | Dengeli, baseline |
| Random Forest | 0.78 | 0.822 | 0.48 | Churn recall düşük |
| **XGBoost** | 0.76 | 0.831 | **0.70** | En çok churn eden müşteriyi yakalıyor |

📌 **Sonuç:** XGBoost churn eden müşterileri en yüksek oranda yakaladığı için en değerli modeldir.  

---

## 📊 Özellik Önemleri (Feature Importance)
XGBoost modeline göre churn üzerinde en kritik faktörler:  
1. **Contract_Month-to-Month** → En büyük churn faktörü.  
2. **InternetService_Fiber optic** → Fiber kullanıcıları daha riskli.  
3. **OnlineSecurity_No** ve **TechSupport_No** → Ek hizmet almayan müşteriler daha çok ayrılıyor.  
4. **Tenure (özellikle 0–12 ay)** → Yeni müşteriler en riskli grup.  
5. **PaymentMethod_Electronic check** → Daha fazla churn riski taşıyor.  

---

## 🎯 İş Önerileri
- **Kontrat Yönetimi:** Aylık kontratlı müşteriler uzun vadeli sözleşmelere yönlendirilmeli.  
- **Fiber İnternet:** Fiyat/performans iyileştirmeleri yapılmalı.  
- **Ek Hizmetler:** OnlineSecurity ve TechSupport paketleri teşvik edilmeli.  
- **Yeni Müşteriler:** İlk yıl için özel kampanyalar uygulanmalı.  
- **Ödeme Yöntemi:** Elektronik çek yerine otomatik ödeme / kredi kartı kullanılmalı.  

---

kaggle :
