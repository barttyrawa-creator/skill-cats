# 🔊 Cat Fortress 2 - Sound Assets Production Sheet

Użyj poniższych parametrów i promptów w generatorach dźwięku AI (np. Stable Audio, ElevenLabs, MyEdit). Zapisz pliki w formacie `.mp3` w głównym folderze gry.

| Nazwa pliku | Długość | Typ | Prompt dla AI | Opis |
|:---|:---|:---|:---|:---|
| `shoot_scout.mp3` | 0.5s | FX | "High-pitched laser pew, cute cat meow hybrid, fast, energetic, 8-bit style" | Szybki "pew" dla Scouta |
| `shoot_heavy.mp3` | 1.0s | FX | "Rapid fire heavy machine gun, mechanical thumping, low cat growl undertone, rhythmic" | Ciężki karabin włóczkowy |
| `shoot_sniper.mp3` | 1.5s | FX | "Loud thunderous boom, distant echo, sharp cat hiss at the end, powerful" | Potężny wystrzał snajperki |
| `shoot_soldier.mp3` | 1.0s | FX | "Cartoon rocket launch, whistling sound, small explosion, cat screech" | Wyrzutnia kłębków |
| `melee_slash.mp3` | 0.4s | FX | "Sharp sword swish, cat claws scratching wood, quick, aggressive" | Atak pazurami |
| `hit_impact.mp3` | 0.3s | FX | "Squishy impact, wet thud, soft cat yelp, cartoonish" | Trafienie przeciwnika |
| `death_meow.mp3` | 1.2s | Voice | "Sad dramatic cat meow, fading out, comical, video game death sound" | Dźwięk porażki |
| `capture_progress.mp3`| Loop | FX | "Bubbling milk sound, rhythmic ticking, purring background, satisfying" | Przejmowanie punktu |
| `win_music.mp3` | 5.0s | Music | "Upbeat 8-bit victory fanfare, heroic cat theme, celebratory, trumpets" | Ekran zwycięstwa |
| `ambient_garden.mp3` | Loop | Amb | "Peaceful garden ambience, chirping birds, light wind, occasional distant purr" | Tło dla mapy Garden |

---

## 🛠️ Jak dodać te dźwięki do kodu?

Kiedy już wygenerujesz i zapiszesz pliki w folderze, będziemy musieli dodać w `index.html` prosty system `AudioContext` lub obiektów `new Audio()`.

### Przykład implementacji (do dodania później):
```javascript
const sounds = {
    shoot_scout: new Audio('shoot_scout.mp3'),
    death: new Audio('death_meow.mp3'),
    // ... reszta
};

// Odtwarzanie:
sounds.shoot_scout.currentTime = 0;
sounds.shoot_scout.play();
```

**Rekomendacja PO:** Skoncentruj się najpierw na `shoot_scout.mp3` i `death_meow.mp3` – to one dają najwięcej satysfakcji na początku!
