<div align="center">

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:0b1220,100:0e7490&height=110&section=header&text=HeadHunter&fontSize=42&fontColor=22d3ee&fontAlignY=54&desc=Drop%20the%20victim's%20head%20on%20a%20kill&descSize=13&descColor=94a3b8&descAlignY=80" width="100%" alt="HeadHunter" />

<p>
<img src="https://img.shields.io/github/v/release/chizzar-dev/HeadHunter?style=flat&label=release&color=06b6d4&labelColor=0b1220" alt="release" />
<img src="https://img.shields.io/badge/Minecraft-1.8%20%E2%80%93%201.21.11-0891b2?style=flat&labelColor=0b1220" alt="Minecraft 1.8 - 1.21.11" />
<img src="https://img.shields.io/badge/Java-8%2B-155e75?style=flat&labelColor=0b1220&logo=openjdk&logoColor=22d3ee" alt="Java 8+" />
<a href="LICENSE"><img src="https://img.shields.io/github/license/chizzar-dev/HeadHunter?style=flat&label=license&color=0e7490&labelColor=0b1220" alt="license" /></a>
</p>

</div>

HeadHunter drops the victim's head when a player is killed, carrying their real skin and the killer's name. Mob heads are optional.

*HeadHunter, bir oyuncu oldurulunce kurbanin kafasini dusurur; kafada gercek skini ve katilin adi yazar. Mob kafalari istege baglidir.*

## Features · Özellikler
- Ölen oyuncunun kafası düşer — üstünde **gerçek skini** görünür, varsayılan Steve/Alex değil
- Kafanın adı ve açıklaması tamamen ayarlanabilir (katil, kurban, tarih)
- Türkçe ilgi eki desteği: `%victim_in%` → *chizzar'ın Kafası*
- Düşme şansı yüzde olarak ayarlanır (ondalıklı yazabilirsin: `12.5`)
- Kafa yere düşsün ya da doğrudan katilin envanterine gitsin
- İsteğe bağlı sunucu geneli duyuru
- **Mob kafaları** — iskelet, zombi, creeper, ender ejderha ve daha fazlası (varsayılan kapalı)
- Dünya bazında kapatma

## Installation · Kurulum
1. [Releases](https://github.com/chizzar-dev/HeadHunter/releases/latest) sayfasından `HeadHunter.jar` dosyasını indir.
2. Sunucunun `plugins/` klasörüne at.
3. Sunucuyu yeniden başlat.
4. `plugins/HeadHunter/config.yml` dosyasından şansı ve yazıları düzenle.

## Commands · Komutlar
| Komut | Açıklama | Yetki |
|-------|----------|-------|
| `/headhunter reload` | Ayarları yeniden yükler | `headhunter.reload` |

**Alias:** `/kafaavi` · `/hh`

## Permissions · Yetkiler
| Yetki | Açıklama | Varsayılan |
|-------|----------|------------|
| `headhunter.reload` | Configi yeniden yükler | op |

## Configuration · Ayarlar
| Anahtar | Açıklama |
|---------|----------|
| `enabled` | Plugin açık mı |
| `chance` | Kafa düşme şansı (0 – 100, ondalıklı olabilir) |
| `only-player-kills` | Sadece oyuncu öldürmelerinde mi düşsün |
| `count-suicide` | Kendini öldürme sayılsın mı |
| `give-to-killer` | Kafa doğrudan katile mi verilsin |
| `disabled-worlds` | Bu dünyalarda kafa düşmez |
| `name` / `lore` | Kafanın adı ve açıklaması |
| `date-format` | Tarih biçimi |
| `mob-heads.enabled` / `chance` | Mob kafaları ve şansı |
| `messages.announce` | Duyuru mesajı (boş = duyuru yok) |

### Yer tutucular

| Kalıp | Anlamı |
| :-- | :-- |
| `%victim%` | Ölen oyuncunun adı |
| `%victim_in%` | İlgi ekli hâli — *chizzar'ın* |
| `%killer%` | Öldüren oyuncunun adı |
| `%killer_in%` | İlgi ekli hâli |
| `%date%` | Ölüm tarihi |

## Notes · Notlar
- Kafaya kurbanın gerçek derisi gömülür. Bunun için sırasıyla modern `PlayerProfile` API'si (1.18+),
  `GameProfile` (1.8 – 1.17) ve son çare olarak isim eşleştirmesi denenir.
- 1.13 öncesinde kafa `SKULL_ITEM:3`, sonrasında `PLAYER_HEAD` olarak oluşturulur; bu otomatik yapılır.

## Building · Derleme
```bash
mvn clean package
```
Çıktı · Output: `target/HeadHunter.jar`

Her push [GitHub Actions](https://github.com/chizzar-dev/HeadHunter/actions/workflows/build.yml) ile derlenir; `v*` etiketli sürümler jar'la birlikte [Releases](https://github.com/chizzar-dev/HeadHunter/releases) sayfasına eklenir.
<br><sub>Every push is built by GitHub Actions; tagged `v*` releases attach the jar.</sub>

## License · Lisans
[MIT](LICENSE) — istediğin gibi kullan, değiştir, dağıt · use, modify and distribute freely

<div align="center"><sub>chizzar-dev · Minecraft plugins for 1.8 – 1.21.11 · <a href="https://discord.gg/forges">Discord</a></sub></div>
