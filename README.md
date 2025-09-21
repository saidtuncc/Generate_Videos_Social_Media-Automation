# 🤖 AI Video Generator with n8n

> **EN:** An end-to-end n8n workflow that turns text ideas into short social videos.  
> **TR:** Metin fikirlerini kısa sosyal videolara dönüştüren uçtan uca bir n8n iş akışı.

---

## 🧭 Overview / Genel Bakış
**EN:**  
This workflow pulls ideas from Google Sheets, generates short captions and scripts with OpenAI, creates images with Flux (PiAPI), converts them to 5s clips with Kling (PiAPI), generates voiceover with ElevenLabs, assembles everything via Creatomate, and uploads the final video to Google Drive. Optional step: bulk-publish to social platforms.

**TR:**  
Bu iş akışı Google Sheets’ten fikirleri çeker, OpenAI ile kısa başlıklar ve senaryo üretir, Flux (PiAPI) ile görseller oluşturur, Kling (PiAPI) ile 5 sn’lik kliplere dönüştürür, ElevenLabs ile seslendirme üretir, Creatomate üzerinden montaj yapar ve final videoyu Google Drive’a yükler. İsteğe bağlı: toplu sosyal platform yükleme.

---

## ✨ Features / Özellikler
- **EN:** Ideas → Captions (OpenAI), Image (Flux), Image→Video (Kling), Script (OpenAI), Voiceover (ElevenLabs), Final montage (Creatomate), Upload (Drive), optional social posting  
- **TR:** Fikir → Başlık (OpenAI), Görsel (Flux), Görsel→Video (Kling), Senaryo (OpenAI), Seslendirme (ElevenLabs), Final montaj (Creatomate), Yükleme (Drive), opsiyonel sosyal medya paylaşımı

---

## ✅ Requirements / Gereksinimler
- **n8n** (self-hosted or Cloud)
- API keys: **OpenAI**, **PiAPI (Flux & Kling)**, **ElevenLabs**, **Creatomate**
- **Google Sheets API** & **Google Drive API** enabled (OAuth)
- (Optional) Social bulk upload service credentials

---

## 📦 Files / Dosyalar
- `workflow.json` — n8n export (import this file into n8n)
- `/docs` or `/screenshots` — (optional) example outputs, template previews

---

## ⚙️ Setup / Kurulum
**EN:**
1. In n8n, go to **Import from File** and select `workflow.json`.  
2. Create **Credentials** for each service (OpenAI, PiAPI, ElevenLabs, Creatomate, Google).  
3. In workflow nodes, reference those credentials and fill required fields.

**TR:**  
1. n8n içinde **Import from File** ile `workflow.json` dosyasını içe aktarın.  
2. Her servis için **Credentials** oluşturun (OpenAI, PiAPI, ElevenLabs, Creatomate, Google).  
3. İlgili node’larda bu kimlik bilgilerini seçip gerekli alanları doldurun.

---

## 🔧 Configuration / Yapılandırma
**EN:**
- **Google Sheets:** Duplicate the sample sheet or connect your own; update the Sheet ID in the node.  
- **Flux (PiAPI):** Choose a model (e.g., `flux1-dev`, `flux1-schnell`).  
- **Kling (PiAPI):** Select mode (`std` cheaper / `pro` higher quality).  
- **Creatomate:** Create a video template and paste its `template_id` in the node.  
- **ElevenLabs:** Pick a **voice_id** and set it in the TTS node.  
- **Drive:** Ensure the Drive node has permission to create public links (if desired).

**TR:**  
- **Google Sheets:** Örnek sayfayı kopyalayın veya kendi sayfanızı bağlayın; node içindeki Sheet ID’yi güncelleyin.  
- **Flux (PiAPI):** Bir model seçin (örn. `flux1-dev`, `flux1-schnell`).  
- **Kling (PiAPI):** Modu seçin (`std` daha ucuz / `pro` daha kaliteli).  
- **Creatomate:** Video şablonu oluşturup `template_id` değerini node’a girin.  
- **ElevenLabs:** Bir **voice_id** seçin ve TTS node’una yazın.  
- **Drive:** Dilerseniz herkese açık link üretme yetkisini etkinleştirin.

---

## ▶️ Run / Çalıştırma
**EN:**  
- Manual: open the workflow and click **Execute Workflow**.  
- Scheduled: enable the trigger (e.g., **Once Per Day**).

**TR:**  
- Manuel: workflow’u açıp **Execute Workflow**’a tıklayın.  
- Zamanlanmış: tetikleyiciyi etkinleştirin (örn. **Once Per Day**).

---

## 📤 Outputs / Çıktılar
**EN:** Final video stored on Google Drive (link returned by the workflow). Optional: record details back to Google Sheets and post to social platforms.  
**TR:** Final video Google Drive’a yüklenir (link workflow çıktısında). İsteğe bağlı: Google Sheets’e kayıt ve sosyal ağlara gönderim.

---

## 💸 Cost Notes / Maliyet Notları
**EN:** Costs vary by model and durations (Flux/Kling/LLM/TTS). Prefer lightweight models and 5s clips while testing.  
**TR:** Maliyetler model ve süreye göre değişir (Flux/Kling/LLM/TTS). Testte düşük maliyetli modelleri ve 5 sn klipleri tercih edin.

---

## 🔐 Security / Güvenlik
**EN:** Store all API keys in **n8n Credentials**—never commit secrets. Control Drive sharing (public vs restricted).  
**TR:** Tüm API anahtarlarını **n8n Credentials** içinde tutun—gizli bilgileri repoya koymayın. Drive paylaşım yetkilerini kontrol edin.

---

## 🛠 Tech Stack / Teknolojiler
n8n • OpenAI API • PiAPI (Flux, Kling) • ElevenLabs API • Creatomate API • Google Sheets/Drive API

---

## 🧪 Quick Test / Hızlı Test
**EN:** Add one idea to the Sheet → run workflow → check the Drive link for audio, captions, montage.  
**TR:** Sheet’e bir fikir ekleyin → workflow’u çalıştırın → Drive linkindeki seste, başlıklarda ve montajda sorun var mı kontrol edin.


