# Content Quality Gates

Bu workflow, `content-skills.zip` içindeki beş yazım becerisini Khopilot pre-launch sistemine kalite kapısı olarak ekler.

Kaynak beceriler:

- `viral-hooks`
- `storytelling`
- `dumbify`
- `anti-ai-writing`
- `voice-dna`

## Nerede Durur?

Bu paket fikir kaynağı değildir. Fikri Khopilot stratejisi seçer; bu paket fikri yayına çıkacak hale getirir.

```text
Khopilot lane seçimi
-> fikir / rota / hedef metrik
-> hook varyantları
-> content quality gates
-> Flow prompt / Palmier / TRIBE
-> yayın
-> metrik
-> winner clone
```

## Gate Sırası

### 1. Viral Hooks Gate

Amaç: ilk 1-2 saniyeyi öldüren sorunları yakalamak.

Kontrol:

- Konu ilk anda belli mi?
- İzleyen bunun kendisiyle ilgili olduğunu anlıyor mu?
- Merak boşluğu var mı?
- A-vs-B kontrastı somut mu?
- "Bekle anlatayım", "POV:" gibi boş giriş var mı?

Khopilot yorumu:

- "Google Maps buna yol diyor" gibi konu net açılır.
- "Motorcu buna karakter testi diyor" gibi kontrast gelir.
- Şok için değil, doğru kişinin durması için yazılır.

### 2. Storytelling Gate

Amaç: hook sonrası videoyu ayakta tutmak.

Kontrol:

- İçerik "and then" diye üst üste bilgi mi yığıyor?
- Beat'ler `but / therefore` mantığıyla akıyor mu?
- Son cümle paylaşılabilir bir "last dab" mi?
- Hikaye gerçek mi, uydurma biyografi yok mu?
- 30 saniye için 60-75 kelime sınırı korunuyor mu?

Khopilot yorumu:

- Rota lore, build-in-public, absürd mini-drama ve talking-head içeriklerinde kullan.
- Saf ürün demosunda hafif uygula; mekanik click-demo için zorlamaya gerek yok.

### 3. Dumbify Gate

Amaç: metni basitleştirmek; fikri küçültmek değil.

Kontrol:

- Hook 6. sınıf, body yaklaşık 8. sınıf seviyesinde mi?
- Bir cümlede tek fikir var mı?
- Jargon hedef kitlenin bildiği şey mi?
- Soyut iddia yerine örnek var mı?

Khopilot yorumu:

- "Nöro-duyusal pre-test" yerine içerikte "hangi video daha canlı duruyor?" denir.
- "Curve intelligence" yerine "virajı geç görmeden önce uyarı" denir.

### 4. Anti-AI Writing Gate

Amaç: metnin jenerik AI reklamı gibi kokmasını engellemek.

Kontrol:

- "Ultimate, revolutionary, game-changing" yok.
- "It's not X, it's Y" gibi boş reframe yok; varsa B somut mu?
- Kategori değil örnek var mı?
- Gereksiz metafor, sunum dili, hype kelimesi yok mu?
- Caption bir insanın yazacağı kadar spesifik mi?

Khopilot yorumu:

- "Sürüş deneyimini dönüştürür" yazma.
- "D915'te viraj bitmiyor, ego bitiyor" gibi sahneye bağlı yaz.

### 5. Voice DNA Gate

Amaç: hesap dili sabitlemek.

Durum:

- Şimdilik voice-dna yok; hesap boş olduğu için "voice unverified" notu düşülür.
- İlk 20 gerçek post/reel/transcript birikince voice-dna çıkarılır.

Khopilot başlangıç sesi:

- Türkçe.
- Direkt.
- Hafif pis komik olabilir.
- Jenerik reklam dili yok.
- Motorcu/arabacı gibi konuşur; marka manifestosu gibi değil.

## İçerik Üretiminde Uygulama

Her içerik brief'inin sonunda şu audit bloğu olmalı:

```text
QUALITY GATES
Viral hook: pass / revise
Story: pass / not applicable / revise
Dumbify: pass / revise
Anti-AI: pass / revise
Voice DNA: unverified / pass
Final action: publish / regenerate hook / rewrite caption / cut body
```

## Hangi İçerikte Hangi Gate Ağır?

| İçerik türü | En ağır gate |
|---|---|
| Reel hook | Viral Hooks |
| Absürd mini-drama | Storytelling + Viral Hooks |
| Carousel | Dumbify + Anti-AI |
| Caption | Anti-AI |
| Threads | Voice DNA + Anti-AI |
| Ürün proof | Dumbify |
| Rota lore | Storytelling + Anti-AI |

## Kill Rules

Şunlardan biri varsa yayınlama:

- Hook konusu 2 saniyede belli değil.
- İçerik Khopilot yerine genel motivasyon sayfası gibi duruyor.
- Caption "premium driving experience" gibi boş marka cümleleriyle dolu.
- Hikaye gerçek olay gibi yazılmış ama gerçek beat yok.
- Mizah var ama ürün/rota/kültür bağlantısı yok.
