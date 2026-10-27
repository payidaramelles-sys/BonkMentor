# BonkMentor

Megabonk için **seçim danışmanı**. Yükseltme ve eşya tekliflerini mevcut karakterine ve silahlarına göre puanlar.

Hiçbir şeyi otomatik seçmez, satın almaz, oyunu veya kaydını değiştirmez. Sadece gösterir — kararı sen verirsin.

---

## Ne yapar?

- **Yükseltme ekranı** — her teklifin köşesinde rozetler: sahip olduğun her silah için bir işaret, artı bir karakter işareti.
  - `++` / `+` iyi · `~` nötr · `x` zararlı veya işe yaramaz · `?` bilinmiyor
- **İpucu (tooltip)** — karta gelince ayrıntılı döküm: hangi silah ne kadar kazanıyor, karakter ne düşünüyor, toplam puan ve yorum (`Güçlü`, `Nötr`, `Zayıf`…).
- **En iyi kart vurgusu** — en yüksek puanlı kartın çevresi ince yeşil çizgiyle işaretlenir.
- **Sandık, Moai (Madagaskar heykeli) ve Şüpheli Adam (şapkalı satıcı)** ekranları aynı rozet ve vurguyla değerlendirilir.
- **Tapınaklar / kule (Charge Shrine)** ve diğer karşılaşma teklifleri de kapsanır.
- **Envanter ipuçları** — sahip olduğun eşya ve silahların ipucuna puan satırı eklenir.
- **Karakter seçimi** — karakter açıklamasının altına `BonkMentor: Saldırı + · Savunma ~ · Hareket + · Fayda + · Başlangıç: Kemik` satırı düşer.

## Puanlama

| Parça | Ağırlık |
| --- | --- |
| Silah ortalaması | %55 |
| Karakter uyumu | %25 |
| Genel fayda | %20 |

Değerler oyunun kendi verisinden okunur. Bilinmeyen veri `?` olarak gösterilir — mod asla sayı uydurmaz.

**Eşyalar:** Oyunda eşyaların istatistik verisi tutulmuyor (87 eşyanın hiçbirinde `statModifiers` dolu değil), etkileri kodun içinde tanımlı. Bu yüzden eşya kartlarında puan **kartta yazan metinden** okunur (`+15% hasar`, `+2 maksimum can` gibi) ve ipucunun sonunda `(kart metninden okundu)` notu çıkar. Metinden sayı okunamazsa işaret `?` kalır.

---

## Kurulum

**Gerekli:** [BepInEx 6 (IL2CPP)](https://thunderstore.io/c/megabonk/p/BepInEx/BepInExPack_Megabonk/)

### Yöntem 1 — Mod manager (önerilen)
r2modman veya Gale ile Megabonk profiline `BonkMentor` paketini ekle.

### Yöntem 2 — Elle
1. Oyunu kapat.
2. `BonkMentor.dll` dosyasını `Megabonk/BepInEx/plugins/` klasörüne kopyala.
3. Oyunu başlat. `BepInEx/LogOutput.log` içinde `BonkMentor 1.0.0 loaded` satırını görmelisin.

## Ayarlar

`BepInEx/config/com.mehme.bonkmentor.cfg` veya oyun içi Configuration Manager:

| Ayar | Varsayılan | Açıklama |
| --- | --- | --- |
| `Genel > Etkin` | `true` | Modu tamamen aç/kapat |
| `Genel > Dil` | `tr` | `tr` veya `en` |
| `Arayüz > İpuçları` | `true` | Ayrıntılı ipucu |
| `Arayüz > En İyi Vurgusu` | `true` | En iyi kart çerçevesi |
| `Arayüz > Vurgu Rengi` | `#19FF59` | Çerçeve rengi |
| `Arayüz > Rozet Ölçeği` | `1.0` | 0.6 – 1.8 |
| `Arayüz > Rozet Köşesi` | `BottomRight` | Rozetlerin yeri |
| `Arayüz > Rozet Arka Planı` | `true` | Rozet arkası koyu şerit |

## Uyumluluk

- Megabonk 1.0.69 (Unity 2023.2.22f1) üzerinde geliştirildi.
- **MegabonkBetterMinimap** ve **StatHUD** ile birlikte test edildi, çakışma yok.
- Tamamen istemci taraflı ve görseldir; çok oyunculuda diğer oyunculara etkisi yoktur.
- Oyun güncellemesinden sonra sınıf isimleri değişirse rozetler susabilir; mod yine de oyunu bozmaz.

## Geri alma

Modu kaldırmak için `BepInEx/plugins/BonkMentor.dll` dosyasını silmek yeterlidir. Oyun dosyalarına hiç dokunulmaz, kayıt dosyaları değiştirilmez.

---

# English

**BonkMentor** is a client-side choice advisor for Megabonk. It rates level-up offers, items, chests, Moai and shop offers against your current character and weapons, and highlights the best card with a thin green outline.

- Badges: one mark per owned weapon plus one character mark. `++` / `+` good · `~` neutral · `x` harmful or useless · `?` unknown.
- Hover a card for a full breakdown. Unknown data stays `?` — the mod never invents numbers.
- Purely visual: it never selects or buys anything, and never touches your save.

## Install

Requires [BepInEx 6 (IL2CPP)](https://thunderstore.io/c/megabonk/p/BepInEx/BepInExPack_Megabonk/).

1. Close the game.
2. Copy `BonkMentor.dll` into `Megabonk/BepInEx/plugins/`.
3. Launch. `BepInEx/LogOutput.log` should contain `BonkMentor 1.0.0 loaded`.

Or install it through r2modman / Gale.

## Notes

- Items in Megabonk expose no stat data (all 87 items have empty `statModifiers`), so item scores are parsed from the card text and the tooltip appends `(read from card text)`.
- Tested with **MegabonkBetterMinimap** and **StatHUD** — no conflicts.
- Uninstall by deleting the DLL. No game or save files are modified.

---

**Bu proje açık kaynak değildir.** Dağıtım paketi ücretsiz kullanılabilir; kaynak kod paylaşılmaz. Ayrıntı: [LICENSE](LICENSE) — *This project is not open source. The distributed build is free to use; the source code is not published.*
