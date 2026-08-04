# Game Education Atlas · Oyun Eğitimi Atlası

**249 higher-education game programmes across 48 countries — every record verified from the institution's own website.**
*48 ülkede 249 yükseköğretim oyun programı — her kayıt kurumun kendi sitesinden doğrulandı.*

🌐 **[Browse the atlas / Katalogu gez](https://gusanmaz.github.io/game-education-atlas/)** ·
📄 **[PDF](catalogue/oyun-programlari.pdf)** ·
📝 **[Markdown](catalogue/OYUN-PROGRAMLARI.md)** ·
🤝 **[Contribute / Katkı ver](CONTRIBUTING.md)**

---

## English

A catalogue of higher-education programmes in **game development, game design and game art**
worldwide. It covers universities, universities of applied sciences, art schools, polytechnics,
vocational colleges and community colleges.

For each programme the atlas records — where the institution publishes it — the degree awarded,
duration, ECTS, language of instruction, tuition, course list, research labs, named faculty, and the
sources used to verify all of it.

**What makes this different from a course-aggregator listing:** every entry was checked against the
**institution's own website**. Aggregator sites are used only as a starting point for finding
candidates, never as the source of a claim. Where a fact could not be verified, the record says so
rather than guessing. Where an institution does not publish its teaching staff, the record explains
that instead of leaving a blank.

**Scope.** Europe · United Kingdom · Türkiye · United States · Canada · Australia · New Zealand ·
Japan · China · South Korea · Singapore · Hong Kong · Taiwan · Israel · Gulf states (UAE, Saudi
Arabia, Qatar, Bahrain, Oman) · Russia · Ukraine · Caucasus (Azerbaijan, Armenia). The Türkiye
section is complete — it is generated directly from the Turkish Higher Education Council's 2026
admission guide and covers **every** programme with "game" in its name. Other countries are added
institution by institution as each is verified.

**A note on level.** The catalogue pays particular attention to **short-cycle higher education**
(EQF level 5 and its equivalents: Portuguese CTeSP, Danish AP, Swedish YH, US Associate of Applied
Science, Ontario College Advanced Diploma, Japanese senmon gakkō, Singaporean polytechnic diploma,
Turkish ön lisans). These programmes are chronically under-represented in international listings,
and short-cycle entries are marked here.

**Language.** The interface is English/Turkish. **Programme descriptions are written in Turkish**;
English translations are very welcome as contributions.

> **Known limitation — Turkish diacritics.** The descriptions were typed without Turkish diacritics
> (`ogrenci` rather than `öğrenci`, `yuksekogretim` rather than `yükseköğretim`). Restoring them
> mechanically is unreliable, because Turkish suffixes carry the diacritics too and a stem-based fix
> leaves text half-corrected. They are being restored by hand, section by section — **this is an easy
> and genuinely useful first contribution.** See [CONTRIBUTING.md](CONTRIBUTING.md#diacritics).

## Türkçe

Dünya genelinde **oyun geliştirme, oyun tasarımı ve oyun sanatı** alanındaki yükseköğretim
programlarının kataloğu. Üniversiteler, uygulamalı bilimler üniversiteleri, sanat okulları,
politeknikler, meslek yüksekokulları ve community college'lar kapsam içinde.

Her program için — kurum yayınladığı ölçüde — verilen derece, süre, AKTS, eğitim dili, ücret, ders
listesi, araştırma laboratuvarları, öğretim üyeleri ve tüm bunların doğrulandığı kaynaklar kayıtlı.

**Aracı listelerden farkı:** her kayıt **kurumun kendi sitesinden** kontrol edildi. Aracı siteler
yalnızca aday bulmak için kullanıldı, hiçbir bilginin kaynağı olarak değil. Doğrulanamayan bir bilgi
varsa kayıt bunu tahmin etmek yerine açıkça söylüyor. Kurum öğretim kadrosunu yayınlamıyorsa, kayıt
boş bırakılmak yerine bunun nedenini yazıyor.

**Düzey vurgusu.** Katalog **kısa döngü yükseköğretime** (EQF 5 ve dengi: Portekiz CTeSP, Danimarka
AP, İsveç YH, ABD Associate of Applied Science, Ontario College Advanced Diploma, Japon senmon
gakkō, Singapur politeknik diploması, Türkiye ön lisans) ayrı bir önem veriyor. Bu programlar
uluslararası listelerde sürekli eksik temsil ediliyor; burada kısa döngü kayıtlar işaretli.

**Türkiye bölümü eksiksizdir** — doğrudan YÖK'ün 2026 tercih kılavuzu verisinden üretilmiştir ve
adında "oyun" geçen **bütün** programları kapsar.

---

## What's in the repository / Depo içeriği

| Path | Contents |
|---|---|
| `catalogue/OYUN-PROGRAMLARI.md` | The full catalogue, grouped by country (Turkish) |
| `catalogue/oyun-programlari.pdf` | Same catalogue as a printable PDF |
| `data/catalogue.json` | The underlying structured data — one record per programme |
| `data/turkiye-yok-2026.json` | Türkiye: 2026 YÖK guide snapshot, all game programmes |
| `docs/` | The website published at GitHub Pages |

`data/catalogue.json` is the source of truth; the Markdown, the PDF and the website are all
generated from it.

## Record structure / Kayıt yapısı

```jsonc
{
  "kayit_id": "40-1",              // record id
  "kurum": "IT University of Copenhagen",
  "sehir": "Kopenhag",             // city
  "ulke": "Danimarka",             // country
  "oyun_odagi": "Yuksek",          // Yuksek = dedicated game programme, Orta = game courses
  "program": "MSc in Games — Games Technology / Games Design ...",
  "derece": "Master of Science",   // degree awarded
  "sure_yil": 2,                   // duration in years
  "ects": 120,
  "ects_kaynak": "bologna-normu",  // present when ECTS is derived from the 60-ECTS year, not read off the page
  "dil": "Ingilizce",              // language of instruction
  "ucret": "AB/AEA vatandaslari icin ucretsiz ...",
  "myo_duzeyi": "",                // set when the programme is short-cycle / associate level
  "dersler": ["..."],              // courses
  "arastirma_lab": [{ "ad": "...", "url": "..." }],
  "hocalar": [{ "ad": "...", "unvan": "...", "alan": "...", "url": "..." }],
  "hoca_notu": "",                 // why faculty names are absent, when they are
  "notlar": "...",                 // free-text observations
  "url": "https://...",            // programme page
  "kaynaklar": ["https://..."],    // verification sources
  "durum": "dogrulandi"            // verified
}
```

## Corrections and additions / Düzeltme ve eklemeler

Programmes close, rename, move faculty and change fees. If you find something out of date — or your
institution is missing — please open an issue or a pull request. The one rule is that a claim must
be backed by the institution's own page. See **[CONTRIBUTING.md](CONTRIBUTING.md)**.

Programlar kapanır, ad değiştirir, kadro değişir, ücretler güncellenir. Güncel olmayan bir şey
görürseniz ya da kurumunuz listede yoksa lütfen issue veya pull request açın. Tek kural: her bilgi
kurumun kendi sayfasına dayanmalı.

## License / Lisans

Content is licensed under **[CC BY 4.0](LICENSE)** — reuse, adapt and redistribute freely, including
commercially, as long as you give attribution.

Suggested citation:

> Usanmaz, G. *Game Education Atlas.* https://github.com/gusanmaz/game-education-atlas (CC BY 4.0)

## Who made this / Kim hazırladı

Compiled by **Güvenç Usanmaz**.
