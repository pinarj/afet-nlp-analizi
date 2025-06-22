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
```python
import matplotlib.pyplot as plt
from collections import Counter

# İhtiyaçlar
ihtiyac_counter = Counter(sum(yardim_df["İhtiyaçlar"], []))
labels, values = zip(*ihtiyac_counter.most_common(10))

plt.figure(figsize=(8,5))
plt.barh(labels, values)
plt.title("En Sık Geçen İhtiyaçlar")
plt.gca().invert_yaxis()
plt.show()
```

![image](https://github.com/user-attachments/assets/ddad23b4-90bb-4456-bf9e-0588b59a3c5b)


### 📍 En Sık Bahsedilen Yerler
```python
from collections import Counter
import matplotlib.pyplot as plt

yer_counter = Counter(sum(yardim_df["Yerler"], []))
etiketler, sayilar = zip(*yer_counter.most_common(10))

plt.figure(figsize=(8, 5))
plt.barh(etiketler, sayilar)
plt.xlabel("Frekans")
plt.title("En Sık Bahsedilen Yerler")
plt.gca().invert_yaxis()
plt.tight_layout()
plt.show()
```

![image](https://github.com/user-attachments/assets/59b17f26-93a4-4bdd-93ff-4366afefb459)



### 🤖 Confusion Matrix (Logistic Regression)
```python
from sklearn.metrics import confusion_matrix
import seaborn as sns
import matplotlib.pyplot as plt

cm = confusion_matrix(y_test, y_pred)
sns.heatmap(cm, annot=True, fmt="d", cmap="Blues")
plt.xlabel("Tahmin")
plt.ylabel("Gerçek")
plt.title("Confusion Matrix")
plt.show()
```

![image](https://github.com/user-attachments/assets/06243c6f-6b72-4191-a03f-651bbac8f30a)


### 💚 Naive Bayes Confusion Matrix
```python
from sklearn.metrics import confusion_matrix
import seaborn as sns
import matplotlib.pyplot as plt

cm_nb = confusion_matrix(y_test, y_pred_nb)
sns.heatmap(cm_nb, annot=True, fmt="d", cmap="Greens")
plt.xlabel("Tahmin")
plt.ylabel("Gerçek")
plt.title("Naive Bayes - Confusion Matrix")
plt.show()
```

![image](https://github.com/user-attachments/assets/1b28a7f2-a9ab-4fed-8194-b1a083064fb3)


### 📈 Duygu Dağılımı Grafiği
```python
import seaborn as sns
import matplotlib.pyplot as plt

sns.countplot(data=yardim_df, x="Duygu")
plt.title("Yardım Tweet’lerinin Duygu Dağılımı")
plt.xlabel("Duygu")
plt.ylabel("Tweet Sayısı")
plt.show()
```

![image](https://github.com/user-attachments/assets/fe370fe7-a3e5-493e-b219-522e8044fc93)


---




