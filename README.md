# Titanic Kaggle Projesi

## Proje Amacı
Titanic gemisi kazasında hangi yolcuların hayatta kaldığını tahmin etmek için makine öğrenmesi modeli geliştirmek.

## Veri Seti
- **train.csv**: Eğitim verisi (özellikler ve hayatta kalma durumu)
- **test.csv**: Test verisi (özellikler)
- **gender_submission.csv**: Örnek gönderim dosyası

Veri setindeki önemli özellikler:
- Pclass (Bilet sınıfı)
- Sex (Cinsiyet)
- Age (Yaş)
- SibSp (Gemideki kardeş/eş sayısı)
- Parch (Gemideki ebeveyn/çocuk sayısı)
- Fare (Bilet ücreti)
- Embarked (Biniş limanı)

## Veri Ön İşleme
- Eksik değerler `SimpleImputer` ile medyan veya en sık görülen değer kullanılarak dolduruldu.
- Kategorik değişkenler `OneHotEncoder` ile sayısallaştırıldı.
- Sürekli değişkenler `StandardScaler` ile ölçeklendirildi.
- `ColumnTransformer` ve `Pipeline` kullanılarak ön işleme adımları entegre edildi.

## Özellik Mühendisliği
- `FamilySize` özelliği oluşturuldu (SibSp + Parch + 1).
- `IsAlone` özelliği eklendi (yalnız yolcu bilgisi).
- `Title` gibi yeni anlamlı özellikler çıkarıldı.
- Gerekli sütunlar seçildi ve işlenmedi.

## Modelleme
- `GradientBoostingClassifier` kullanıldı.
- Veri `train_test_split` ile eğitim ve doğrulama setlerine ayrıldı.
- Model pipeline içerisinde eğitim ve test edildi.
- Model performansı `accuracy_score` ile ölçüldü.

## Sonuçlar
- Kaggle test setinde elde edilen skor: **0.77033** (yani %77.03 doğruluk).

## Projeyi Çalıştırma Adımları
1. Depoyu klonlayın:  
   ```bash
   git clone https://github.com/kullaniciadi/titanic-kaggle.git
   cd titanic-kaggle
