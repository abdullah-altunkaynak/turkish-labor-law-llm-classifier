# Turkish Labor Law LLM Classifier

Bu depo, Türk İş Hukuku metinlerinin otomatik sınıflandırılması üzerine geliştirilen **SLM (Small Language Model)** tabanlı modelleri, veri setlerini ve değerlendirme sonuçlarını içermektedir.

## 📌 Proje Özeti
Bu çalışma, düşük parametreli dil modellerinin (TinyLlama, Gemma, Qwen, SmolLM) Türk İş Hukuku alanındaki 8 farklı sınıflandırma görevindeki performanslarını benchmark etmektedir.

## 🚀 Proje Kaynakları
Aşağıdaki bağlantılardan modellerimize ve veri setimize ulaşabilirsiniz:

### Modeller (Hugging Face)
- [TinyLlama-1.1B-TR-Law](https://huggingface.co/abdullah-altunkaynak/TinyLlama-1.1B-TR-Law) - *En Yüksek Başarım*
- [Gemma-2B-TR-Law](https://huggingface.co/abdullah-altunkaynak/Gemma-2B-TR-Law)
- [Qwen-2.5-1.5B-TR-Law](https://huggingface.co/abdullah-altunkaynak/Qwen-2.5-1.5B-TR-Law)
- [SmolLM2-360M-TR-Law](https://huggingface.co/abdullah-altunkaynak/SmolLM2-360M-TR-Law)

### Veri Seti
- [Turkish Labor Law Dataset](https://huggingface.co/datasets/abdullah-altunkaynak/Turkish-Labor-Law-Dataset)

## 📊 Metodoloji ve Denetim
- **Eğitim:** QLoRA (4-bit quantization) yöntemi kullanılmıştır.
- **Veri Doğrulama:** Veri setinin "Gold Standard" kısmı, bağımsız bir hukuk uzmanı (Avukat) tarafından çapraz doğrulanmıştır (Inter-Annotator Agreement analizi gerçekleştirilmiştir).
- **Benchmark:** Modeller, 3 farklı seed (42, 123, 999) ile test edilmiş ve ortalama sonuçlar raporlanmıştır.

## 🛠 Kurulum
```bash
git clone [https://github.com/](https://github.com/)[KullanıcıAdınız]/turkish-labor-law-llm-classifier
cd turkish-labor-law-llm-classifier
pip install -r requirements.txt
python inference.py --model_name "abdullah-altunkaynak/TinyLlama-1.1B-TR-Law" --text "Mobbing iddiaları hakkında..."