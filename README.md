# 🔤 Türkçe Eksik Karakter Tamamlama: RNN, LSTM ve GRU

Bu projede, Türkçe metinlerde eksik bırakılmış karakterlerin derin öğrenme yöntemleri ile tamamlanması amaçlanmıştır.  
Girdi olarak bazı harfleri `_` ile maskelenmiş cümleler kullanılmış, modelden ise bu cümlelerin doğru hâlini üretmesi beklenmiştir.

## Örnek

<img width="1264" height="472" alt="image" src="https://github.com/user-attachments/assets/6a504171-39a4-4cc3-8959-6cf682c8822a" />


---

## 📌 Projenin Amacı

Bu çalışmada, Türkçe cümlelerde eksik bırakılan karakterleri tahmin edebilen bir model geliştirilmiştir.  
Karakter seviyesinde çalışan farklı tekrarlayan sinir ağı mimarileri karşılaştırılmıştır.

Kullanılan mimariler:

- RNN
- LSTM
- GRU
- Geliştirilmiş sürüm olarak çift yönlü yapılar:
  - BiLSTM
  - BiGRU

---

## 🗂 Veri Seti

Projede **GEC-Turk / BOUN** veri seti temel alınmıştır.  
Temiz hedef cümleler kullanılarak yapay biçimde bozulmuş giriş cümleleri üretilmiştir.

### Uygulanan ön işleme adımları

- tekrar eden satırların silinmesi
- metin normalizasyonu
- gereksiz karakterlerin temizlenmesi
- çok uzun cümlelerin en fazla **10 kelimelik** parçalara bölünmesi
- bazı karakterlerin `_` ile değiştirilerek bozuk giriş verisinin oluşturulması

---

## ⚙️ Yöntem

Problem, **karakter seviyesinde sıralı tahmin problemi** olarak ele alınmıştır.

### İş akışı

1. Temiz Türkçe cümlelerin okunması  
2. Metinlerin normalize edilmesi  
3. Tekrarlı satırların kaldırılması  
4. Uzun cümlelerin parçalara ayrılması  
5. Eksik karakterli giriş verisinin oluşturulması  
6. Karakter sözlüğünün oluşturulması  
7. RNN tabanlı modellerin eğitilmesi  
8. Örnek cümleler üzerinde tahmin yapılması  

---

## 🧠 Model Mimarisi

Model genel olarak şu katmanlardan oluşmaktadır:

- **Embedding katmanı**
- **RNN / LSTM / GRU katmanı**
- **Linear katman** ile karakter tahmini

Bu çalışma karakter seviyesinde yapıldığı için, girişteki her karaktere karşılık çıktı tarafında bir karakter tahmin edilmektedir.

---

## 🛠 Kullanılan Teknolojiler

- Python
- PyTorch
- Google Colab
- Git / GitHub

---

## 🚀 Projeyi Çalıştırma

### 1. Repoyu klonlayın

```bash
git clone https://github.com/sevvalsaritas/eksikKarakterTamamlama.git
cd eksikKarakterTamamlama
