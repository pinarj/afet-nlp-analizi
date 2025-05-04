# afet-nlp-analizi


# 🌍 Afet Anında Sosyal Medya Üzerinden Yardım Çağrılarının NLP ile Tespiti

Bu proje, 6 Şubat 2023 depremi gibi büyük afetlerde sosyal medya (özellikle Twitter) üzerinden paylaşılan yardım çağrılarını analiz etmeyi hedefler. Doğal Dil İşleme (NLP) teknikleri kullanılarak ihtiyaç, yer, iletişim bilgileri çıkarılmış ve yardım içerip içermediği sınıflandırılmıştır.

---

## 🔍 Proje Amaçları

- Tweet'lerden **ihtiyaç (örn. su, çadır)**, **yer (örn. Hatay, Kahramanmaraş)** ve **telefon numarası** bilgilerini çıkarmak
- Yardım çağrısı içerip içermediğini sınıflandırmak
- Tweet’lerdeki **duygusal durumu (negatif, pozitif, nötr)** analiz etmek

---

## 📊 Uygulanan Adımlar

1. CSV verisinin açılması ve filtrelenmesi (`Class == 1.0`)
2. Metin temizleme (URL, @mention, noktalama, sayılar çıkarıldı)
3. Regex ve keyword listeleriyle:
   - **İhtiyaç** ve **yer** bilgisi çıkarımı
   - **Telefon numarası** tespiti
4. En sık geçen ihtiyaç ve yerlerin grafikle gösterimi  
5. Logistic Regression & Naive Bayes modelleri ile sınıflandırma  
6. TextBlob ile **duygu analizi** ve dağılım grafiği

---

## 🛠️ Kullanılan Teknolojiler

- Python, Pandas, Matplotlib, Seaborn
- Scikit-learn (Logistic Regression, Naive Bayes)
- TextBlob (duygu analizi)
- Regular Expressions (re)
- CountVectorizer

---

## 🖼️ Görselleştirme Örnekleri

### ✅ En Sık Geçen İhtiyaçlar
![image](https://github.com/user-attachments/assets/ddad23b4-90bb-4456-bf9e-0588b59a3c5b)


### 📍 En Sık Bahsedilen Yerler
![image](https://github.com/user-attachments/assets/8d82eff2-89e6-4666-91da-38a05efad573)


### 🤖 Confusion Matrix (Logistic Regression)
![image](https://github.com/user-attachments/assets/06243c6f-6b72-4191-a03f-651bbac8f30a)


### 💚 Naive Bayes Confusion Matrix
![image](https://github.com/user-attachments/assets/1b28a7f2-a9ab-4fed-8194-b1a083064fb3)


### 📈 Duygu Dağılımı Grafiği
![image](https://github.com/user-attachments/assets/fe370fe7-a3e5-493e-b219-522e8044fc93)


---

## ▶️ Google Colab Üzerinde Çalıştır

📌 Projeyi Colab’da çalıştırmak için:  
👉 [Google Colab Notebook](https://colab.research.google.com/drive/1lkNZMhEXxw3f4YxZgPWLSQL71_58YLzy?usp=sharing)





