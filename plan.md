# 🐈 Cat Fortress 2 - Realistyczny Plan (Standalone Edition)

**Cel:** Stworzenie wciągającej gry split-screen, która nie wymaga zewnętrznych plików (dźwięków, modeli, tekstur) i działa idealnie na samej klawiaturze.

---

## 🚀 Faza 1: "Visual Audio" i Feeling (Zamiast dźwięków)
*Skoro nie mamy plików .mp3, użyjemy kodu, by "pokazać" dźwięk.*

- [ ] **Onomatopeje na ekranie:** Przy strzale Snajpera pojawia się tekst "BOOM!", przy Scoutcie "PEW PEW!", a przy śmierci "MEOW!".
- [ ] **Knockback (Odrzut):** Fizyczne odpychanie gracza przy trafieniu. To buduje poczucie "mocy" broni bez dźwięku.
- [ ] **Screen Shake (Trzęsienie ekranu):** Delikatne potrząśnięcie kamerą danego gracza przy strzelaniu lub otrzymywaniu obrażeń.
- [ ] **Muzzle Flash:** Proceduralne rozbłyski światła (żółte kule/stożki) przy lufie przy każdym strzale.

---

## 🗺️ Faza 2: Mechanika Taktyczna (Proceduralny Content)
*Różnorodność bez dodawania modeli 3D.*

- [ ] **Klasa: Medyk (Proceduralny):** Strzela zielonymi kulkami mleka, które leczą sojusznika. Promień leczenia (Line helper) łączący graczy.
- [ ] **Power-upy na mapie:** 
    - **Pudełko Kocimiętki:** Zmienia kolor kota na tęczowy i podwaja szybkość na 5 sek.
    - **Złota Rybka:** Pojawia się na środku mapy, daje 100% HP.
- [ ] **Dynamiczne Pułapki:** Czerwone strefy na mapie (np. "Plama Wody"), które spowalniają gracza.

---

## 🤖 Faza 3: AI i Single Player (Realistyczne Bots)
*Aby gra nie była martwa, gdy nie masz z kim grać.*

- [ ] **Kocie Boty:** Prosta logika "widzę wroga -> idź w jego stronę -> jeśli dystans < X -> strzelaj".
- [ ] **NavMesh Lite:** Boty omijają istniejące przeszkody na mapie.

---

## 🎨 Faza 4: Estetyka "TF2 Style" (Tylko kod)
- [ ] **Toon Outlines:** Dodanie czarnych krawędzi do modeli kotów (efekt komiksowy), co ukryje prostotę modeli.
- [ ] **Lepsze UI:** Pasek HP zmieniający kolor (Zielony -> Żółty -> Czerwony).

---

## 💡 Przykład Rozwiązania: "Soczysty Strzał" (Knockback + Screen Shake)

To jest klucz do tego, żeby gra była "grywalna jak TF2". Nawet bez dźwięku gracz musi czuć siłę uderzenia.

**Jak to zaimplementować (Przykład logiczny):**
1. **Knockback:** Gdy pocisk trafia w gracza, obliczamy wektor od pocisku do gracza. Dodajemy ten wektor do `velocity` gracza, co powoduje jego "odrzucenie".
2. **Screen Shake:** W funkcji `updateCamera` dodajemy losowe przesunięcie `Math.random() * intensywność`, które zmniejsza się co klatkę.

---
**Rekomendacja PO:** Zacznijmy od implementacji **Knockbacku**, ponieważ to drastycznie zmienia dynamikę walki - Snajper może odpychać Scouta, uniemożliwiając mu podejście.
