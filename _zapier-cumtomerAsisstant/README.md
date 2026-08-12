# 🤖 Asisstant_Agent - Zapier & AI Powered Customer Assistant

![Zapier Entegrasyonu](https://img.shields.io/badge/Zapier-Automation-FF4A00?style=for-the-badge&logo=zapier&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-AI%20Analysis-412991?style=for-the-badge&logo=openai&logoColor=white)
![Google Sheets](https://img.shields.io/badge/Google%20Sheets-Database-34A853?style=for-the-badge&logo=googlesheets&logoColor=white)
![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=for-the-badge)


<img width="1917" height="866" alt="image" src="https://github.com/user-attachments/assets/bad228c1-95d4-4e83-9dac-bd7ab23db08e" />


<img width="1354" height="541" alt="image" src="https://github.com/user-attachments/assets/40b63c58-f062-444f-aa7d-e93aa45184e8" />


**Asisstant_Agent**, müşteri taleplerini otomatize etmek, veri analizlerini anlık olarak gerçekleştirmek ve sonuçları veritabanı/tablo sistemlerine aktarmak için geliştirilmiş yapay zekâ destekli bir otomasyon asistanıdır.

Bu proje; **Zapier**, **LLM (OpenAI/ChatGPT)** ve **Google Sheets** entegrasyonlarını kullanarak gelen verileri kategorize eder, analiz eder ve ilgili tablolara otomatik olarak işler.

---

## 📌 Özellikler

* ⚡ **Otomatik Tetikleme (Real-time Triggers):** Google Sheets veya Webhook üzerinden gelen müşteri verilerini anında yakalar.
* 🧠 **Yapay Zekâ Analizi:** Gelen mesajların duygu analizini, kategori tespitini ve özetlemesini otomatik olarak gerçekleştirir.
* 🔄 **Dinamik Veri Güncelleme:** AI tarafından üretilen çıktıları ve yanıtları ilgili tablo satırına (`Update Row`) geri yazar.
* 🚀 **Ölçeklenebilir Akış (Zapier Canvas):** Kolay yönetilebilir ve geliştirilebilir iş akışı mimarisi.

---

## 🛠️ Çalışma Mantığı (Workflow)

```text
[ Müşteri Talebi / Yeni Satır ] 
               │
               ▼
   ( Google Sheets Trigger )
               │
               ▼
      ( AI Agent Analysis ) ──► [ Niyet / Duygu / Kategori Analizi ]
               │
               ▼
     ( Google Sheets Update ) ──► [ Yanıtı & Sonucu Tabloya Yaz ]
Tetikleyici (Trigger): Google Sheets tablosuna yeni bir müşteri talebi veya veri eklendiğinde akış başlatılır.

AI Analiz Adımı: Zapier AI / OpenAI entegrasyonu ile gelen metin işlenir, sınıflandırılır ve çözüm yanıtı oluşturulur.

Güncelleme & Eylem (Action): Elde edilen yapay zekâ analizi ve yanıt, Google Sheets'teki ilgili satıra işlenerek süreç tamamlanır.

🚀 Kurulum ve Yapılandırma
1. Ön Gereksinimler
Bir Zapier hesabı

Google Sheets erişimi ve hedef tablo yapısı

OpenAI API Key (veya Zapier AI Actions yetkilendirmesi)

2. Zapier Şablonunu İçe Aktarma
İş akışını hızlıca kendi Zapier hesabınıza aktarmak için aşağıdaki şablonu kullanabilirsiniz:

🔗 Zapier Şablonu: Analyze and Update Google Sheets with AI

3. Yapılandırma Adımları
Şablonu Zapier hesabınızda açın (Use this Zap).

Google Sheets adımında takip edilecek tabloyu ve çalışma sayfasını seçin.

AI analiz adımındaki Prompt alanını ihtiyacınıza göre düzenleyin (Örn: Müşteri mesajını analiz et ve kategori belirle).

Güncelleme adımında AI çıktılarının yazılacağı sütunları eşleştirin ve Zap'i aktif hale getirin.

<img width="1917" height="866" alt="image" src="https://github.com/user-attachments/assets/bad228c1-95d4-4e83-9dac-bd7ab23db08e" />


<img width="1354" height="541" alt="image" src="https://github.com/user-attachments/assets/40b63c58-f062-444f-aa7d-e93aa45184e8" />
