# 📬 AI Agent Email Assistant (n8n Workflow)

Bu proje, gelen kutunuzdaki e-postaları her sabah otomatik olarak analiz eden, önemli aksiyonları, takvim toplantılarını ve okunmamış mesajları derleyerek size şık ve mobil uyumlu bir **HTML e-posta özeti** gönderen **n8n AI Asistanı** iş akışıdır.

---

<img width="1918" height="821" alt="image" src="https://github.com/user-attachments/assets/c1e6eb4f-9716-42bd-b9b3-55ef6f7a6033" />



## 🌟 Öne Çıkan Özellikler

- ⏰ **Zamanlanmış Çalışma (Schedule Trigger):** Her sabah saat `07:00`'de otomatik olarak tetiklenir.
- 🤖 **Yapay Zeka Destekli Analiz (AI Agent & OpenAI / Gemini):**
  - Bir önceki güne ait e-postaları tarar.
  - Yanıt verilmesi gereken ve aksiyon bekleyen e-postaları tespit eder.
  - Takvime eklenmesi gereken toplantıları ayıklar.
  - Okunmamış ama kritik öneme sahip mesajları belirler.
  - Her e-posta için 2-3 cümlelik öz anlatımlı özetler çıkarır.
- 🎨 **Zengin ve Mobil Uyumlu HTML Tasarımı:**
  - Emoji kullanımı ve renkli başlıklar ile görsel ayrım.
  - Aksiyon gerektiren durumlar için tablolu görünüm.
  - Mobil cihazlarda rahat okunabilir düzen.
- 📧 **Gmail Entegrasyonu:** E-postaları okuma ve hazırlanan HTML özetini doğrudan e-posta kutunuza gönderme araçlarına sahiptir.

---

## 🛠️ Kullanılan Teknolojiler ve Düğümler (Nodes)

- **n8n:** İş akışı otomasyon platformu.
- **Schedule Trigger:** Zamanlanmış tetikleyici.
- **AI Agent (`@n8n/n8n-nodes-langchain.agent`):** E-postaları analiz edip kararlar alan ve HTML çıktısını oluşturan yapay zeka ajanı.
- **OpenAI / Gemini Chat Model:** Dil modeli entegrasyonu (Varsayılan olarak `gpt-4.1-mini` bağlıdır, istenirse Google Gemini `gemini-2.5-pro` seçilebilir).
- **Gmail Tool (`n8n-nodes-base.gmailTool`):** AI Agent'ın geçmiş e-postaları çekmesini sağlayan araç.
- **Gmail Node (`n8n-nodes-base.gmail`):** Oluşturulan HTML özet e-postasını gönderen düğüm.

---

## 🚀 Kurulum ve Kullanım

### 1. Hazırlık
- Çalışan bir **n8n** kurulumuna (Self-hosted veya n8n Cloud) sahip olduğunuzdan emin olun.
- Gerekli API hesaplarını hazırlayın:
  - **Gmail OAuth2** Hesabı
  - **OpenAI API Key** veya **Google Gemini API Key**

### 2. İş Akışını n8n'e Aktarma (Import)
1. Repository içindeki workflow JSON dosyasını indirin veya kodunu kopyalayın.
2. n8n arayüzünde sol menüden **Workflows** bölümüne gidin.
3. Sağ üstteki **`...`** menüsünden **Import from File** (veya **Import from URL / Paste**) seçeneğini tıklayarak JSON dosyasını yükleyin.

### 3. Kimlik Bilgilerini (Credentials) Tanımlama
İş akışını içe aktardıktan sonra düğümlerdeki kırmızı uyarıları gidermek için ilgili hesaplarınızı bağlayın:
- **Gmail OAuth2 Credentials:** 
  - `Get many messages in Gmail` ve `Send a message` düğümlerine Gmail hesabınızı bağlayın.
- **OpenAI / Gemini Credentials:**
  - `OpenAI Chat Model` düğümüne OpenAI API anahtarınızı bağlayın.

### 4. Özelleştirme
- **Alıcı E-posta Adresi:** `Send a message` (Gmail) düğümünü açarak `Send To` alanındaki `test@example.com` adresini kendi e-posta adresinizle değiştirin.
- **Tetiklenme Saati:** `Schedule Trigger` düğümünden çalışma saatini (varsayılan 07:00) dilerseniz değiştirebilirsiniz.

### 5. Aktifleştirme
İş akışının üst kısmında bulunan **Active** anahtarını `ON` konumuna getirerek otomasyonu başlatın.

---

## 🧾 Örnek Çıktı Formatı

AI Agent, gelen e-postalarınızı analiz ederek aşağıdaki yapıya benzer mobil uyumlu ve şık bir HTML e-postası üretir:

```text
📬 Günlük E-Posta Özeti – 6 Temmuz 2025

📌 1. Aksiyon Gerektiren E-Postalar
+--------------+----------------+------------+------------------+
| Gönderen     | Konu           | Özet       | Durum            |
+--------------+----------------+------------+------------------+
| Ayşe Yılmaz  | Proje Sunumu   | Mail Özeti | Cevap Bekleniyor |
| Can Demir    | Satış Raporları| Mail Özeti | Eksik Dosya      |
+--------------+----------------+------------+------------------+

📅 2. Takvime Eklenmesi Gerekenler
🕑 Yarın 14:00 → Finans Toplantısı (Ali Kara)

📥 3. Okunmamış Önemli E-Postalar
🔔 [Konu: Strateji Belgesi] – Gönderen: CEO – Özet: Email özeti

📝 Not: Bu özet, yalnızca önceliklendirme amaçlıdır.
