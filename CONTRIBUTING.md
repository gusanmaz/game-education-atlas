# Contributing / Katkı

Corrections and additions are very welcome. **[English](#english) · [Türkçe](#türkçe)**

---

## English

### The one rule

**Every factual claim must be traceable to the institution's own website.**

Aggregator sites (bachelorsportal, mastersportal, educations.com, studyin\*, ranking sites, agency
pages) are fine for *finding* a programme, but they are not acceptable as the source of a fact. They
are frequently out of date and they routinely attribute programmes to the wrong institution — during
the compilation of this atlas, aggregators wrongly placed a game programme at Warsaw University of
Technology, mixed up two universities in Milan, and listed a school that had already closed.

If you cannot verify something from the institution, that is useful information too: say so in the
record rather than leaving a confident-looking blank. Records already use two fields for this —
`hoca_notu` (why faculty names are not listed) and free text in `notlar`.

### What to contribute

| | |
|---|---|
| **A missing institution** | Anything teaching game development, design or art at higher-education level |
| **A correction** | Programme renamed, closed, moved faculty, changed language or fees |
| **A deepening** | Course lists, research labs, named faculty for a record that lacks them |
| **A translation** | Programme descriptions are in Turkish; English versions are welcome |

Please keep the scope: **higher education**. Bootcamps, private short courses and secondary-school
programmes are out of scope, however good they are.

### How

1. Edit **`data/catalogue.json`** — that file is the source of truth. The Markdown, the PDF and the
   website are generated from it, so do not edit those directly.
2. Follow the existing record structure (documented in the [README](README.md#record-structure--kayıt-yapısı)).
3. Put every URL you used in `kaynaklar`, and the main programme page in `url`.
4. Open a pull request describing what you changed and, briefly, how you verified it.

If JSON is not your thing, **just open an issue** with the institution name and a link. That is a
genuinely useful contribution and someone will do the data entry.

### Diacritics

The Turkish descriptions were typed without diacritics — `ogrenci` instead of `öğrenci`,
`gelistirme` instead of `geliştirme`. **Fixing a country's records by hand is a perfect first
contribution:** no research needed, just careful reading.

A mechanical fix was tried and abandoned: a stem-based replacement corrects `gelistir` → `geliştir`
but leaves the suffix untouched, producing half-corrected text like `SEVİYEMIZ`, which reads worse
than plain ASCII. If you take this on, please do a whole country at a time so the file never sits in
a mixed state.

**Do not** change these fields while doing it — they are used as keys by the generators:
`oyun_odagi` (`Yuksek` / `Orta` / `Dusuk`), `ulke`, `durum`, `kayit_id`, `kurum_id`, `ects_kaynak`.

### Style notes

- `oyun_odagi`: `"Yuksek"` = the institution has a dedicated game programme; `"Orta"` = game is
  taught inside a broader programme; `"Dusuk"` = no meaningful game teaching.
- `myo_duzeyi`: fill this only for short-cycle / associate-level qualifications, with the local name
  of the award (`"CTeSP — EQF 5"`, `"Associate of Applied Science (AAS)"`, …).
- `ects`: if you take the number from the institution, leave `ects_kaynak` out. If you derived it
  from the Bologna 60-ECTS year, set `"ects_kaynak": "bologna-normu"` so readers know.
- Prefer what the institution calls itself over what rankings call it.

---

## Türkçe

### Tek kural

**Her bilgi kurumun kendi sitesinden doğrulanabilir olmalı.**

Aracı siteler (bachelorsportal, mastersportal, educations.com, studyin\*, sıralama siteleri, danışmanlık
sayfaları) bir programı *bulmak* için uygundur ama bir bilginin kaynağı olarak kabul edilmez. Sık sık
güncelliğini yitiriyorlar ve programları yanlış kuruma atfediyorlar — bu atlas hazırlanırken aracı
siteler bir oyun programını Varşova Teknik Üniversitesi'ne yanlış atfetti, Milano'daki iki
üniversiteyi birbirine karıştırdı ve çoktan kapanmış bir okulu listeledi.

Bir şeyi kurumdan doğrulayamıyorsanız bu da değerli bir bilgidir: kaydı emin görünen bir boşlukla
bırakmak yerine durumu yazın. Katalogda bunun için iki alan var — `hoca_notu` (öğretim üyesi
isimlerinin neden olmadığı) ve `notlar` içindeki serbest metin.

### Ne katkı verilebilir

| | |
|---|---|
| **Eksik kurum** | Yükseköğretim düzeyinde oyun geliştirme, tasarımı veya sanatı öğreten her kurum |
| **Düzeltme** | Program adı değişmiş, kapanmış, fakülte değiştirmiş, dil veya ücret güncellenmiş |
| **Derinleştirme** | Eksik olan ders listesi, araştırma laboratuvarı, öğretim üyesi bilgisi |
| **Çeviri** | Program açıklamaları Türkçe; İngilizce çeviriler memnuniyetle karşılanır |

Kapsamı koruyalım: **yükseköğretim**. Bootcamp'ler, özel kısa kurslar ve lise düzeyi programlar — ne
kadar iyi olurlarsa olsunlar — kapsam dışı.

### Nasıl

1. **`data/catalogue.json`** dosyasını düzenleyin — asıl kaynak odur. Markdown, PDF ve web sitesi
   bu dosyadan üretilir, onları doğrudan düzenlemeyin.
2. Mevcut kayıt yapısını izleyin ([README](README.md#record-structure--kayıt-yapısı)'de belgeli).
3. Kullandığınız her bağlantıyı `kaynaklar` alanına, ana program sayfasını `url` alanına koyun.
4. Neyi değiştirdiğinizi ve kısaca nasıl doğruladığınızı anlatan bir pull request açın.

JSON ile uğraşmak istemiyorsanız **sadece issue açın** — kurum adı ve bir bağlantı yeterli. Bu da
gerçekten işe yarar bir katkıdır, veri girişini biri yapar.

### Biçim notları

- `oyun_odagi`: `"Yuksek"` = kurumun ayrı bir oyun programı var; `"Orta"` = oyun daha geniş bir
  programın içinde veriliyor; `"Dusuk"` = kayda değer oyun eğitimi yok.
- `myo_duzeyi`: yalnızca kısa döngü / ön lisans düzeyi nitelikler için, yerel derece adıyla doldurun.
- `ects`: sayıyı kurumdan aldıysanız `ects_kaynak` alanını hiç yazmayın. Bologna 60 AKTS/yıl
  normundan türettiyseniz `"ects_kaynak": "bologna-normu"` yazın ki okur farkı bilsin.
- Kurumun kendini nasıl adlandırdığını, sıralama sitelerinin adlandırmasına tercih edin.

---

## Code of conduct

Be decent to each other. Disagreements about a fact are settled by looking at the institution's page,
not by argument. Contributions are credited in the commit history; if you would like to be named in
the README as a contributor, say so in your pull request.
