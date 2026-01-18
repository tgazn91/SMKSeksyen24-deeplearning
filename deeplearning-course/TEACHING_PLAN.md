# Kelas Deep Learning untuk Pelajar SMK
## Fast.ai Course - Belajar Sambil Buat! 🚀

**Masa:** 9:00 AM - 1:00 PM
**Lokasi:** SMK Seksyen 24, Shah Alam
**Pendekatan:** Hands-on dulu, teori kemudian (cara Jeremy Howard)

---

## 🎯 Apa Yang Korang Akan Belajar Hari Ini?

Bayangkan korang boleh buat:
- **App yang kenal makanan Malaysia** - Snap gambar, AI bagitau nasi lemak ke roti canai!
- **Bot yang baca review Shopee** - Positive ke negative?
- **Sistem recommendation macam Netflix/Spotify** - "Sebab awak suka ini..."

Semua ni possible dengan **Deep Learning**! Dan korang akan buat hari ini! 🔥

---

## 📅 Jadual Hari Ini

| Masa | Durasi | Aktiviti |
|------|--------|----------|
| 9:00 - 9:15 | 15 min | 🎬 Ice Breaking: AI dalam kehidupan seharian |
| 9:15 - 10:15 | 60 min | 🍜 **Lesson 1:** Buat AI Kenal Makanan Malaysia! |
| 10:15 - 10:30 | 15 min | ☕ Rehat (Minum air, stretch!) |
| 10:30 - 11:30 | 60 min | 💬 **Lesson 2:** AI Baca Review & Komen |
| 11:30 - 11:45 | 15 min | 🧃 Rehat |
| 11:45 - 12:45 | 60 min | 🎬 **Lesson 3:** Buat Sistem Recommendation |
| 12:45 - 1:00 | 15 min | 🎤 Q&A + Apa Seterusnya? |

---

## 🎬 Ice Breaking (9:00 - 9:15)

### "AI Dah Ada Sekeliling Kita!"

**Tanya pelajar:**
- Siapa guna TikTok? 📱 → AI yang suggest video FYP korang!
- Siapa pernah guna Grab? 🚗 → AI yang calculate harga & ETA
- Siapa main Mobile Legends? 🎮 → AI yang match korang dengan player lain
- Siapa shopping Shopee? 🛒 → AI yang recommend "You might also like..."

**Mind-blown moment:**
> "Semua benda ni guna Deep Learning. Dan hari ni, korang akan buat sendiri!"

---

## 🍜 Lesson 1: AI Kenal Makanan Malaysia (9:15 - 10:15)

### Objektif
Buat AI yang boleh bezakan nasi lemak, roti canai, teh tarik, dan lain-lain!

### Kenapa Best?
- Relatable - makanan yang korang makan setiap hari
- Visual - nampak result terus
- Instagram-worthy - boleh show off! 📸

### Key Concepts (Explain Simply)
| Term Sains | Bahasa Kita |
|------------|-------------|
| Transfer Learning | "Copy homework" - guna model yang dah pandai, train sikit je |
| Neural Network | Otak tiruan - macam otak kita tapi dalam komputer |
| Training | Ajar AI dengan banyak contoh |
| Epoch | Berapa kali AI ulang belajar semua gambar |

### Aktiviti Hands-on
1. **Demo:** Train model kenal kucing vs anjing (5 minit)
2. **Challenge:** Extend untuk makanan Malaysia!
3. **Competition:** Siapa dapat accuracy paling tinggi? 🏆

### Discussion Points
- "Macam mana Grab Food suggest restoran dekat korang?"
- "Kenapa TikTok filter boleh detect muka?"

---

## 💬 Lesson 2: AI Baca Sentiment (10:30 - 11:30)

### Objektif
Buat AI yang faham sama ada review/komen tu positive atau negative!

### Real-world Examples
- **Shopee reviews:** "Barang sampai cepat, quality tiptop!" → ⭐ Positive
- **Twitter/X:** "Laaa apasal service slow sangat 😤" → 👎 Negative
- **YouTube comments:** "Gila best video ni bang!" → ⭐ Positive

### Key Concepts
| Term | Maksud |
|------|--------|
| NLP | Natural Language Processing - AI faham bahasa manusia |
| Tokenization | Pecahkan ayat jadi words/parts |
| Sentiment | Feeling/mood dalam text |

### Aktiviti Hands-on
1. **Demo:** Train sentiment classifier dengan movie reviews
2. **Test:** Cuba dengan ayat Manglish!
3. **Challenge:** Boleh ke AI faham "best gila" = positive? 🤔

### Fun Activity
Bagi students tulis review pasal:
- Kantin sekolah
- Cikgu favourite
- Game favourite

Tengok AI boleh detect sentiment dengan betul ke tak!

---

## 🎬 Lesson 3: Sistem Recommendation (11:45 - 12:45)

### Objektif
Faham macam mana Netflix/Spotify/TikTok suggest content untuk korang!

### Part A: Data Prediction (30 min)
Predict outcomes dari structured data - macam predict siapa akan score A dalam SPM! 📊

### Part B: Recommendation System (30 min)
Buat mini Netflix - suggest movies based on what users suka!

### Key Concepts
| Term | Contoh |
|------|--------|
| Collaborative Filtering | "Orang yang suka A juga suka B" |
| Embeddings | Represent setiap user/item sebagai numbers |
| Latent Factors | Hidden patterns (genre preference, etc.) |

### Mind-blown Moment
> "TikTok FYP korang berbeza sebab AI dah learn pattern korang - video apa korang stop scroll, berapa lama tengok, apa yang korang like!"

### Discussion
- Privacy concerns - AI tau sangat banyak pasal kita!
- Filter bubble - kita hanya nampak apa yang kita suka

---

## 🎤 Q&A + Next Steps (12:45 - 1:00)

### Resources untuk Belajar Lagi
1. **course.fast.ai** - FREE full course (English, ada subtitle)
2. **Kaggle.com** - Platform competition AI, ada prizes! 💰
3. **Google Colab** - FREE GPU untuk train model

### Homework Challenge 🏠
1. Pilih satu projek:
   - Classifier untuk K-pop groups
   - Sentiment analyzer untuk tweet pasal BLACKPINK vs BTS
   - Makanan classifier yang lebih banyak categories
2. Train model
3. Share result dalam group WhatsApp kelas!

### Career Paths 🎯
- **Data Scientist** - Gaji: RM8,000 - RM25,000/bulan
- **AI Engineer** - Gaji: RM10,000 - RM30,000/bulan
- **ML Researcher** - Kerja dengan Google, Microsoft, Grab!

> "Korang form 4/5 sekarang. Kalau start belajar AI sekarang, by the time masuk uni, korang dah pro!" 💪

---

## 🛠️ Technical Setup

### Sebelum Kelas (Cikgu)
```bash
cd deeplearning-course
uv run jupyter notebook
```

### Kalau Guna Google Colab (Pelajar)
1. Buka colab.research.google.com
2. Upload notebook
3. Runtime → Change runtime type → GPU
4. Run semua cells!

### Troubleshooting Common Issues
| Problem | Solution |
|---------|----------|
| "Module not found" | `!pip install fastai` |
| "CUDA out of memory" | Restart runtime, guna batch size kecil |
| "Download slow" | Sabar, atau guna data yang dah download |

---

## 📝 Tips untuk Cikgu

### Engagement Strategies
1. **Gamification:** Siapa dapat accuracy tertinggi dapat hadiah!
2. **Real examples:** Guna contoh dari apps yang budak-budak guna
3. **Pair programming:** 2 orang 1 laptop, discuss sama-sama
4. **Quick wins:** Pastikan setiap student dapat run at least 1 model

### Jangan Buat
❌ Terlalu fokus pada math/theory
❌ Lecture style - kena hands-on!
❌ Expect semua orang sama speed

### Buat
✅ Celebrate small wins
✅ Relate dengan kehidupan seharian
✅ Encourage experimentation
✅ "Salah pun takpe, kita belajar dari error!"

---

## 🎉 Expected Outcomes

By end of class, students should:
1. ✅ Faham basic concept deep learning
2. ✅ Dah train at least 2-3 models sendiri
3. ✅ Boleh explain pada kawan macam mana AI "belajar"
4. ✅ Excited untuk explore lebih! 🚀

---

*"The best way to learn is by doing. Jom kita buat AI!"* 🇲🇾
