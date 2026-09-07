# 📊 Redukcija Dimenzionalnosti nad Iris Skupom Podataka Primjenom PCA

Ovaj projekat prikazuje praktičnu primjenu **Metode Glavnih Komponenti (Principal Component Analysis – PCA)** nad standardnim *Iris* skupom podataka korišćenjem biblioteka `scikit-learn` i `matplotlib` u Python-u.

Glavni cilj projekta je kompresija četvorodimenzionalnog (4D) prostora osobina na 2D i 3D podprostore uz minimalan gubitak informacija, kao i poređenje ručnog definisanja broja komponenti u odnosu na automatsku selekciju primjenom praga objašnjene varijanse.

---

## 🛠️ Funkcionalnosti i Metodologija

1. **Pretprocesiranje Podataka:**
   - Učitavanje *Iris* skupa podataka (150 uzoraka, 4 osobine, 3 klase: *Setosa*, *Versicolor*, *Virginica*).
   - Standardizacija osobina primjenom `StandardScaler`-a ($\mu = 0, \sigma = 1$) radi obezbeđivanja ravnopravnog uticaja svih atributa na proces dekompozicije.

2. **Uporedna Analiza 4 PCA Varijante:**
   - **Varijanta 1 (Ručno 3D):** Eksplicitno podešavanje na 3 komponente ($n\_components = 3$).
   - **Varijanta 2 (Prag 99% 3D):** Automatska selekcija komponenti za očuvanje najmanje $99\%$ varijanse ($n\_components = 0.99$).
   - **Varijanta 3 (Ručno 2D):** Eksplicitno podešavanje na 2 komponente ($n\_components = 2$).
   - **Varijanta 4 (Prag 95% 2D):** Automatska selekcija komponenti za očuvanje najmanje $95\%$ varijanse ($n\_components = 0.95$).

3. **Vizuelizacija:**
   - Generisanje $2 	imes 2$ mreže grafika sa 3D i 2D *scatter plot* prikazima razdvajanja klasa.

---

## 📊 Pregled Rezultata Eksperimenta

| Varijanta | Režim Selekcije | Zadati Kriterijum | Dobijeno Komponenti | Objašnjena Varijansa | Tip Vizuelizacije |
| :--- | :--- | :---: | :---: | :---: | :---: |
| **1. Ručno 3D** | Eksplicitan broj | 3 komponente | **3** | **99.48%** | 3D Scatter Plot |
| **2. Prag 99%** | Automatski prema varijansi | 0.99 varijanse | **3** | **99.48%** | 3D Scatter Plot |
| **3. Ručno 2D** | Eksplicitan broj | 2 komponente | **2** | **95.81%** | 2D Scatter Plot |
| **4. Prag 95%** | Automatski prema varijansi | 0.95 varijanse | **2** | **95.81%** | 2D Scatter Plot |

### 💡 Ključni Zaključci
- **Efikasna Kompresija:** Redukcijom sa 4D na 2D prostor zadržava se **95.81%** informacija (gubitak svega **4.19%**), što 2D ravan čini optimalnom za vizuelnu prezentaciju.
- **Separabilnost Klasa:** Klasa *Setosa* je u potpunosti linearno odvojiva već na prvoj glavnoj komponenti (PC1), dok *Versicolor* i *Virginica* formiraju jasne klastere uz blago preklapanje na graničnom području.

---

## 🚀 Pokretanje Projekta

### Preduvjeti
Potrebno je imati instaliran Python (verzija 3.8 ili novija) i sledeće pakete:
```bash
pip install numpy matplotlib scikit-learn
```

### Pokretanje Skripte
Klonirajte repozitorijum ili preuzmite `sd.ipynb` fajl, a zatim pokrenite skriptu iz terminala:
```bash
python sd.ipynb
```

---

## 📁 Struktura Koda

```text
├── sd.ipynb          # Glavna Python skripta sa PCA transformacijama i Matplotlib vizuelizacijom
└── README.md        # Dokumentacija projekta
```
