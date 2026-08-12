

<img width="807" height="525" alt="image" src="https://github.com/user-attachments/assets/27fec11b-0437-4cbf-b711-0f0f78f7907d" />

# Make-DataAnalysisAssistant (Make.com) — Blueprint

Bu repo, Make.com üzerinde oluşturulmuş **Integration Make AI Agent** senaryosunun blueprint (JSON) export’unu içerir.

Repo: `Asisstant_Agent/Make-DataAnalysisAssistant`  
Blueprint dosyası: `Integration Make AI Agent.blueprint.json`

## Ne yapar?
- Bir **Custom Mailhook** adresine gelen e-postayı alır.
- **AI Agent**, bağlı **Postgres MCP** araçlarını kullanarak e-postadaki veritabanı sorusunu analiz eder ve yanıt üretir.
- Üretilen yanıtı **Gmail** üzerinden e-postayı gönderen kişiye geri gönderir.

## İçerik
- `Integration Make AI Agent.blueprint.json` — Make senaryo blueprint’i (export)

## Kurulum (Make’e import)
1) Make.com’da yeni bir senaryo oluştur (veya boş bir senaryo aç).  
2) **Import blueprint** ile `Integration Make AI Agent.blueprint.json` dosyasını içe aktar.  
3) Import sonrası aşağıdaki bağlantıları yeniden bağla (blueprint bağlantıları taşımaz):
   - **OpenAI (AI Agent)** bağlantısı (API key ile)
   - **Gmail** bağlantısı (gmail.send + gmail.readonly izinleri)
   - **MCP (PostgreMCP)** bağlantısı (veritabanına erişim için)

> Not: Import eden kişi bu bağlantıları kendi hesabında yeniden seçmek zorundadır.

## Mailhook (Tetikleyici)
Senaryo bir **Custom Mailhook** ile tetiklenir. Import sonrası Make sana yeni bir mailhook adresi üretir.

- Mailhook adresi (import sonrası oluşacak): `YOUR_MAILHOOK_ADDRESS@hook...make.com`

### Hızlı test
1) Senaryoda **Run once** başlat.  
2) Mailhook adresine bir test e-postası gönder.  
   Örnek içerik:
   - Subject: `DB soru`
   - Body: `Bugün kayıt olan kullanıcı sayısı kaç?`

Beklenen: Agent DB’den yanıtı çıkarır ve Gmail üzerinden sana (gönderene) cevap gönderir.



<img width="1918" height="861" alt="image" src="https://github.com/user-attachments/assets/8a622468-b800-48a8-b8b9-c3a5a6462467" />



