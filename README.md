# Kural Tabanlı Müşteri Segmentasyonu Projesi

Bu proje, **MIUUL - Python Programming for Data Science** eğitimi kapsamında gerçekleştirilmiştir.  
Amacımız, bir oyun şirketinin satış verilerini kullanarak **kural tabanlı sınıflandırma** yöntemiyle müşteri segmentleri oluşturmak ve yeni müşterilerin şirkete ortalama ne kadar gelir getirebileceğini tahmin etmektir.  

## Proje Amacı
- Demografik ve cihaz bilgilerini kullanarak **seviye tabanlı müşteri tanımları (persona)** oluşturmak  
- Bu müşteri tanımlarını (persona) ortalama gelire göre segmentlere ayırmak  
- Yeni müşterileri uygun segmente sınıflandırmak  
- Yeni müşterilerin şirkete getireceği ortalama geliri tahmin etmek  

Örneğin:  
Türkiye’den IOS kullanan 25 yaşındaki bir erkek müşterinin şirkete ortalama ne kadar gelir kazandırabileceği hesaplanabilmektedir.  

---

## Veri Seti
Veri seti (`persona.csv`), uluslararası bir oyun şirketinin satış kayıtlarından oluşmaktadır. Her satır bir işlem kaydını temsil eder; aynı müşteri birden fazla kez yer alabilir.  

- **PRICE** : Harcama tutarı  
- **SOURCE** : Cihaz türü (Android / iOS)  
- **SEX** : Müşteri cinsiyeti  
- **COUNTRY** : Müşteri ülkesi  
- **AGE** : Müşteri yaşı  

> **Not:** Veri seti MIUUL tarafından eğitim kapsamında sağlanmıştır ve bu repoda paylaşılmamaktadır. Projeyi çalıştırmak için `data/` klasörüne `persona.csv` dosyasını eklemeniz gerekmektedir.  

---

## Proje Adımları
Proje kapsamında şu adımlar gerçekleştirilmiştir:  

1. **Veri Keşfi (EDA)**  
   - Değişkenlerin incelenmesi  
   - Frekans, toplam gelir ve ortalama değerlerin hesaplanması  

2. **Özellik Mühendisliği (Feature Engineering)**  
   - **AGE** değişkeni kategorik aralıklara dönüştürüldü (örn. `0_18`, `19_23`, `24_30`, `31_40`, `41_66`)  
   - **Seviye tabanlı müşteri tanımları (persona)** oluşturuldu (örn. `TUR_IOS_FEMALE_31_40`)  

3. **Segmentasyon**  
   - Personalar ortalama gelire göre gruplandı  
   - 4 segmente (A, B, C, D) ayrıldı  
   - Segmentlerin ortalama, maksimum ve toplam gelirleri hesaplandı  

4. **Kural Tabanlı Sınıflandırma**  
   - Yeni müşteriler segmentlere atandı  
   - Beklenen gelirleri hesaplandı  

---

## Örnek Çıktılar

- **Persona Örneği**  
```
COUNTRY   SOURCE   SEX      AGE_CAT   PRICE   customers_level_based
TUR       IOS      MALE     31_40     54.0    TUR_IOS_MALE_31_40
```

- **Segment Örneği**  
```
SEGMENT    Price_Mean   Price_Max   Price_Sum
A          55.4         75.0        12500
B          45.3         70.0        9500
C          35.8         60.0        8700
D          25.4         50.0        6500
```

- **Yeni Müşteri Örneği**  
- 33 yaşında Android kullanan bir Türk kadını → **C segmenti**, ortalama ≈ **35.2**  
- 35 yaşında iOS kullanan bir Fransız kadını → **B segmenti**, ortalama ≈ **49.0**  

---

## Kullanılan Teknolojiler
- Python  
- Pandas  
- NumPy  

---

## Notlar
- Bu proje, **MIUUL Python Programming for Data Science** eğitimi kapsamında yapılmıştır.  
- Veri seti gizlilik nedeniyle paylaşılmamaktadır.  
