# Khopilot Growth Lab

Konu-bağımsız bir short-form **virality engine** — içeriği değil, "her seferinde izleten" içeriği üreten *sistemi* kurar. İlk tenant Khopilot (pre-launch motor/araba viraj kültürü), ama motor her konuya uygulanır: tenant değişir, rig sabit kalır.

Amaç: uygulama yayına çıkmadan önce Instagram/Threads hesabında doğru **hook'u** bulup test etmek; takipçi, merak, topluluk ve winner hook biriktirmek. Pre-launch'ta install satılmaz.

## Sistem (kanonik)

- **İki kaldıraç:** watch time (hayatta kalma) + sends per reach (takipçi-olmayana breakout). Sıra sabit: önce HOLD, sonra SEND.
- **Rig:** her video bir **5 beat × 3 kanal** (görsel/ses/yazı) matrisi; hook beatinde üç kanal da aynı şeyi söyler (mute-first).
- **Survival-gate:** açılış ilk 1.5s'de muted dikkati hak etmeli — *soru VEYA görsel-stake VEYA niş-uyum* (biri yeter). Gerçek fail modu: düşük-stake + mundane + niş-dışı. Tek kural risk-flag'dir, kesin hüküm değil.
- **Kalibrasyon disiplini:** tahmin = hipotez; gerçek skip/completion/sends ile yanlışla; kuralı veriden güncelle. Teori-bazlı önden sıralamaya güvenme, çeşitli bahisleri test et.

## Yapı

- `skill/khopilot-growth-lab/SKILL.md`: motorun giriş noktası.
- `skill/khopilot-growth-lab/references/`: `system` (rig), `hook-engine`, `algorithm-2026` (Meta mekaniği), `calibration` (tahmin→veri disiplini), `content-quality-gates`, `content-brief`, `metrics-intake`, ve Khopilot tenant paketi (`prelaunch-growth-system`, `prelaunch-idea-bank`, `production-stack`).
- `skill/khopilot-growth-lab/agents/`: `hook-smith` → `script-architect` → `retention-editor` → (winner) `flow-prompt-director` + `vo-director` → `metric-judge`. Ayrıca `openai.yaml` (Codex arayüzü).
- `workflows/`, `ideas/`, `templates/`: operasyon akışları, fikir bankası, şablonlar.

## Codex Skill

Global kurulum hedefi:

```bash
~/.codex/skills/khopilot-growth-lab -> /Users/ebuodin/Developer/khopilot-growth-lab/skill/khopilot-growth-lab
```

Skill adı: `$khopilot-growth-lab`

Örnek kullanım:

```text
Use $khopilot-growth-lab to create today's pre-launch Instagram Reel brief for a natural motorcycle route hook.
```

## Ana Kural

App hazır değilken install satma. Hesap karakteri, rota kültürü, makara, tartışma, takip sebebi ve winner hook üret.
