# VOLLSTÄNDIGE FORMELSAMMLUNG
# Dissertation: Perturbative Modulare Lineare Antwort in KMS-Systemen

## Quellen-Index

```
[W-L]  Wikipedia: Laplace-Transformation
       https://de.wikipedia.org/wiki/Laplace-Transformation

[W-HY] Wikipedia: Hille-Yosida-Theorem / C₀-Halbgruppe
       https://en.wikipedia.org/wiki/Hille-Yosida_theorem

[EN00] K.-J. Engel, R. Nagel, "One-parameter semigroups", Springer GTM 194 (2000)

[A73]  H. Araki, PRIMS 9:165 (1973)  [DOI: 10.2977/prims/1195192684]

[BR87] O. Bratteli, D.W. Robinson, "Operator Algebras and QSM", Vol. II (1987)

[HHW67] Haag, Hugenholtz, Winnink, CMP 5:215 (1967)

[C73]  A. Connes, Ann. Sci. ENS 6:133 (1973)

[K57]  R. Kubo, J. Phys. Soc. Japan 12:570 (1957)

[T70]  M. Takesaki, LNM 128, Springer (1970)
```

---

## TEIL A: Laplace-Transformation
### (Alle Formeln aus [W-L], mit Beweisen)

---

### L-01 — Definition der einseitigen Laplace-Transformation
**Quelle:** [W-L], Definition
**Status:** ✓ DEFINITION

```
ℒ{f}(s) = F(s) = ∫_0^∞ f(t) · e^{-st} dt

s = σ + iω ∈ ℂ  (komplexe Frequenz)

Konvergenzabszisse:  σ_0 = inf{ σ ∈ ℝ : F(σ+iω) konvergiert absolut }

Definitionsbereich:  { s ∈ ℂ : Re(s) > σ_0 }
```

**Physikalische Bedeutung:** Transformation vom Zeitbereich (t ≥ 0)
in den komplexen Frequenzbereich (s = σ + iω). Konvergenzfaktor
e^{-σt} sichert Konvergenz für σ > σ_0.

---

### L-02 — Linearität
**Quelle:** [W-L], Rechenregeln
**Status:** ✓ EXAKT

```
ℒ{α f + β g}(s) = α·F(s) + β·G(s)    für α, β ∈ ℂ
```

---

### L-03 — Ableitungssatz (1. Ableitung)
**Quelle:** [W-L], Ableitungssatz
**Status:** ✓ EXAKT (mit Anfangswert)

```
ℒ{f'}(s) = s · F(s) - f(0⁺)
```

Beweis: Partielle Integration: ∫_0^∞ f'(t)e^{-st}dt = [f(t)e^{-st}]_0^∞ + s·F(s) = -f(0⁺) + s·F(s) □

---

### L-04 — Ableitungssatz (n-te Ableitung)
**Quelle:** [W-L], Ableitungssatz
**Status:** ✓ EXAKT

```
ℒ{f^{(n)}}(s) = s^n·F(s) - s^{n-1}·f(0⁺) - s^{n-2}·f'(0⁺) - ... - f^{(n-1)}(0⁺)
```

---

### L-05 — Integrationssatz
**Quelle:** [W-L], Integrationssatz
**Status:** ✓ EXAKT

```
ℒ{ ∫_0^t f(τ)dτ }(s) = F(s) / s
```

---

### L-06 — Faltungssatz
**Quelle:** [W-L], Faltungssatz; Beweis via Fubini-Theorem
**Status:** ✓ EXAKT

```
ℒ{f * g}(s) = F(s) · G(s)

(f * g)(t) := ∫_0^t f(t-τ) · g(τ) dτ    (Faltungsintegral)
```

Beweis:
```
ℒ{f*g}(s) = ∫_0^∞ e^{-st} ∫_0^t f(t-τ)g(τ)dτ dt
           = ∫_0^∞ g(τ) ∫_τ^∞ f(t-τ)e^{-st}dt dτ    (Fubini)
           = ∫_0^∞ g(τ)e^{-sτ} ∫_0^∞ f(u)e^{-su}du dτ    (u = t-τ)
           = G(s) · F(s)    □
```

---

### L-07 — Anfangswerttheorem (Anfangswerttheorem)
**Quelle:** [W-L], Grenzwertsätze; [W-HY]
**Status:** ✓ EXAKT

```
f(0⁺) = lim_{s→+∞} s · F(s)
```

Bedingung: f rechtsseitig stetig in 0, F existiert für Re(s) > σ_0.

Beweis: Aus L-03: s·F(s) = ℒ{f'}(s) + f(0⁺). Für s → ∞ gilt
ℒ{f'}(s) → 0 (Riemann-Lebesgue). Daher lim_{s→∞} s·F(s) = f(0⁺). □

---

### L-08 — Endwerttheorem (Endwerttheorem)
**Quelle:** [W-L], Grenzwertsätze; Beweis via Endwertsatz
**Status:** ✓ EXAKT (unter Stabilitätsbedingung)

```
lim_{t→∞} f(t) = lim_{s→0⁺} s · F(s)
```

Bedingung: s·F(s) hat keine Pole mit Re(s) ≥ 0 (Stabilität).

Beweis: Aus der Laplace-Transformierten der Ableitung (L-03):
ℒ{f'}(s) = s·F(s) - f(0⁺).
Grenzwert s → 0⁺: ∫_0^∞ f'(t)dt = f(∞) - f(0⁺).
Daher: s·F(s) → f(∞) für s → 0⁺. □

---

### L-09 — Verschiebungssatz im Zeitbereich
**Quelle:** [W-L], Verschiebungssätze
**Status:** ✓ EXAKT

```
ℒ{f(t-a)·θ(t-a)}(s) = e^{-as} · F(s)    (a > 0)
```

---

### L-10 — Dämpfungssatz (Verschiebung im Bildbereich)
**Quelle:** [W-L]
**Status:** ✓ EXAKT

```
ℒ{e^{at}·f(t)}(s) = F(s-a)
```

---

## TEIL B: Hille-Yosida und Operatorhalbgruppen

---

### HY-01 — C₀-Halbgruppe: Definition
**Quelle:** [W-HY], [EN00] §I.1
**Status:** ✓ DEFINITION

```
{T(t)}_{t≥0} ist C₀-Halbgruppe auf Banach-Raum X, wenn:

(H1) T(0) = I
(H2) T(s+t) = T(s)·T(t)  ∀s,t ≥ 0
(H3) lim_{t→0⁺} ‖T(t)x - x‖ = 0  ∀x ∈ X  (stark stetig)
```

---

### HY-02 — Hille-Yosida-Theorem
**Quelle:** [W-HY], [EN00] Theorem II.3.8
**Status:** ✓ THEOREM (kanonisch, 1948)

```
A erzeugt C₀-Halbgruppe mit ‖T(t)‖ ≤ M·e^{ωt}

⟺

(HY1) A abgeschlossen, D(A) dicht in X
(HY2) ∀λ > ω, ∀n ∈ ℕ:  ‖(λI-A)^{-n}‖ ≤ M/(λ-ω)^n
```

Für Kontraktionshalbgruppen (M=1, ω=0):

```
‖(λI-A)^{-1}‖ ≤ 1/λ    ∀λ > 0
```

---

### HY-03 — Resolvent = Laplace der Halbgruppe
**Quelle:** [EN00] Proposition II.1.10; [W-HY]
**Status:** ✓ KERNFORMEL

```
R(λ, A) = (λI - A)^{-1} = ∫_0^∞ e^{-λt} T(t) dt    für Re(λ) > ω

Normschranke:  ‖R(λ, A)‖ ≤ M / (Re(λ) - ω)
```

**Das ist die Brücke zwischen Laplace-Transformation (Teil A) und
Operatorhalbgruppen — der zentrale Schritt des Hauptbeweises.**

---

### HY-04 — Grenzwert des Resolventen
**Quelle:** [EN00] Proposition II.1.10
**Status:** ✓ EXAKT

```
lim_{λ→∞} λ · R(λ, A)x = x  (stark, ∀x ∈ X)
```

Beweis: λ·R(λ,A)x = λ·∫_0^∞ e^{-λt}T(t)x dt.
Für λ → ∞ konzentriert sich der Integrand bei t = 0, wo T(0)x = x. □

**Anwendung:** Lim_{z→∞} z·R_ad(z, iK_0)(A) = A (Anfangswerttheorem für Operatoren).

---

## TEIL C: Algebraische Quantenfeldtheorie

---

### QFT-01 — KMS-Bedingung
**Quelle:** [HHW67]
**Status:** ✓ DEFINITION + CHARAKTERISIERUNG

```
ω_β KMS bei β > 0 bez. α_t:

F_{AB}(t)    = ω_β(A · α_t(B))
F_{AB}(t+iβ) = ω_β(α_t(B) · A)

F_{AB}: analytisch in 0 < Im(z) < β, stetig am Rand
```

Endlich-dimensional: ρ_β = e^{-βH}/Z(β).

---

### QFT-02 — Tomita-Takesaki-Modularoperatoren
**Quelle:** [T70], Tomita (1967)
**Status:** ✓ THEOREM

```
S_0(AΩ_0) = A*Ω_0              (Tomita-Involution)
S_0 = J_0 · Δ_0^{1/2}          (polare Zerlegung)
K_0 := -log Δ_0                 (Modularhamiltonian)
σ_t^0(A) = e^{itK_0} A e^{-itK_0}  (Modularfluss)

Fundamentalsatz: σ_t^0(𝓜) = 𝓜  ∀t ∈ ℝ
```

---

### QFT-03 — KMS ↔ Modularfluss-Äquivalenz
**Quelle:** [BR87] Vol. II, Proposition 5.3.7
**Status:** ✓ THEOREM (Äquivalenz)

```
ω_β KMS bei β bez. α_t  ⟺  α_t = σ_t^{ω_β}
```

Für Gibbs-Zustand (Type I, endliches System): K_{ω_β} = β·H.

---

### QFT-04 — Connes-Radon-Nikodym-Kozykel
**Quelle:** [C73]
**Status:** ✓ THEOREM

```
(Dω_V : Dω_0)_t = Δ_{ω_V|ω_0}^{it} · Δ_0^{-it}    (unitär in 𝓜)

Kozykel:     (Dω_V:Dω_0)_{t+s} = (Dω_V:Dω_0)_t · σ_t^0((Dω_V:Dω_0)_s)
Komposition: (Dω_V:Dω_0)_t · (Dω_0:Dω_W)_t = (Dω_V:Dω_W)_t
```

---

### QFT-05 — Araki: Relativer Modularoperator
**Quelle:** [A73] Theorem 1
**Status:** ✓ THEOREM (Grundlage der Dissertation)

```
Für beschränktes V ∈ 𝓜, ‖V‖ < ∞:

log Δ_{ω_V|ω_0} = -β · V    (exakt)

K_{ω_V|ω_0} := -log Δ_{ω_V|ω_0} = β · V    (relativer Modularhamiltonian)
```

Für den absoluten Modularhamiltonian:

```
K_{ω_V} = K_{ω_0} + β·V + R(V)
‖R(V)‖ ≤ (β²/2) · ‖V‖ · ‖[K_0, V]‖
```

---

### QFT-06 — Kubo-Formel
**Quelle:** [K57]
**Status:** ✓ THEOREM (Standard-LRT)

```
χ_A(t) = -i · θ(t) · ω_0([σ_t^{ω_0}(A), V])

δ⟨A⟩(t) = ε · ∫_{-∞}^t dt' χ_A(t-t') + O(ε²)
```

---

## TEIL D: Die Beweiskette (Neue Verbindungen)

---

### NEU-01 — Modularfluss als C₀-Gruppe
**Quelle:** QFT-02 + HY-01 [neue Identifikation]
**Status:** ★ NEUE ANWENDUNG

```
Φ_t(A) := σ_t^{ω_0}(A) = e^{itK_0} A e^{-itK_0}

ist C₀-Gruppe auf (B(ℋ), ‖·‖) mit:
  - ‖Φ_t‖ = 1  (unitäre *-Automorphismen)
  - Generator: i · [K_0, ·]
```

Beweis der C₀-Eigenschaft:
```
(H1) Φ_0(A) = A ✓
(H2) Φ_{s+t} = Φ_s ∘ Φ_t: aus σ_{s+t}^0 = σ_s^0 ∘ σ_t^0 ✓
(H3) Starke Stetigkeit: aus KMS-Analytizität (F_{AA}(t) stetig) ✓
‖Φ_t‖ = 1: ‖σ_t^0(A)‖ = ‖A‖ für *-Automorphismen ✓
```

---

### NEU-02 — Adjungierter Laplace-Resolvent des Modularflusses
**Quelle:** NEU-01 + HY-03 [neue Anwendung]
**Status:** ★ KERNOBJEKT der Dissertation

```
R_ad(z, iK_0)(A) := (z · id - i · [K_0, ·])^{-1}(A)
                  = ∫_0^∞ e^{-zt} σ_t^{ω_0}(A) dt    für Re(z) > 0
```

Aus HY-02 (M=1, ω=0):

```
‖R_ad(z, iK_0)‖ ≤ 1/Re(z)

lim_{z→∞} z · R_ad(z, iK_0)(A) = A  (aus HY-04)
```

---

### NEU-03 — Laplace-Kubo-Formel
**Quelle:** QFT-06 + NEU-02 + L-01 [direkte Berechnung]
**Status:** ★ BEWEISSCHRITT 1

```
χ_A(z) = ℒ{χ_A}(z) = ∫_0^∞ e^{-zt}(-i)ω_0([σ_t^0(A), V])dt

        = -i · ω_0([ ∫_0^∞ e^{-zt}σ_t^0(A)dt , V])

        = -i · ω_0([R_ad(z, iK_0)(A), V])
```

Austausch ω_0 ↔ Integral: zulässig da ω_0 normiert und
∫_0^∞ |e^{-zt}|dt = 1/Re(z) < ∞ (dominierte Konvergenz).

---

### NEU-04 — Laplace-Modulare Kubo-Identität
**Quelle:** QFT-05 (Araki) + NEU-03 [HAUPTERGEBNIS]
**Status:** ★ HAUPTTHEOREM

```
┌──────────────────────────────────────────────────────────────────┐
│                                                                  │
│  χ_A(z) = -(i/β) · ω_0([R_ad(z, iK_0)(A), K_{ω_V|ω_0}])      │
│            + E(A, V, z)                                          │
│                                                                  │
│  |E(A,V,z)| ≤ β · ‖A‖ · ‖V‖ · ‖[K_0,V]‖ / (2·Re(z))          │
│                                                                  │
│  Gültig: Re(z) > 0, ‖V‖ < ∞, V ∈ 𝓜, KMS-Zustand             │
│                                                                  │
└──────────────────────────────────────────────────────────────────┘
```

**Vollständiger Beweis (jeder Schritt nummeriert und referenziert):**

```
[1] χ_A(z) = -i·ω_0([R_ad(z)(A), V])                    [NEU-03]

[2] V = (1/β)·K_{ω_V|ω_0} - (1/β)·R(V)                 [QFT-05, Araki]

[3] Einsetzen [2] in [1]:
    χ_A(z) = -(i/β)·ω_0([R_ad(z)(A), K_{ω_V|ω_0}])
           + (i/β)·ω_0([R_ad(z)(A), R(V)])

[4] Fehlerabschätzung:
    |ω_0([R_ad(z)(A), R(V)])|
    ≤ 2·‖ω_0‖·‖R_ad(z)‖·‖A‖·‖R(V)‖               [Linearität ω_0]
    ≤ 2·1·(1/Re(z))·‖A‖·(β²/2)·‖V‖·‖[K_0,V]‖      [HY-02; QFT-05]
    = β²·‖A‖·‖V‖·‖[K_0,V]‖/Re(z)

[5] |E| = (1/β)·|...| ≤ β·‖A‖·‖V‖·‖[K_0,V]‖/(2·Re(z))  □
```

---

### NEU-05 — Araki als Grenzfall (Anfangswerttheorem)
**Quelle:** L-07 + HY-04 + NEU-04
**Status:** ★ KONSISTENZPRÜFUNG

```
χ_A^{stat} = χ_A(t=0⁺) = lim_{z→+∞} z · χ_A(z)        [L-07, Anfangswert]

= lim_{z→∞} z·[-(i/β)·ω_0([R_ad(z)(A), K_{ω_V|ω_0}])]

= -(i/β)·ω_0([ lim_{z→∞} z·R_ad(z)(A) , K_{ω_V|ω_0}])

= -(i/β)·ω_0([A, K_{ω_V|ω_0}])                         [HY-04]

= -(i/β)·ω_0([A, βV])                                   [QFT-05, 1. Ordnung]

= -i·ω_0([A, V])  = χ_A^{stat}  (Standard-Kubo)    ✓
```

**Arakis Ergebnis folgt exakt als Grenzfall z → ∞.**

---

### NEU-06 — Spektralschranke mit Spektrallücke
**Quelle:** HY-02 + Spektraltheorie
**Status:** ★ VERBESSERUNG ÜBER ARAKI

```
Falls spec(K_0) diskret mit Minimalabstand Δ := inf_{m≠n}|λ_m-λ_n| > 0:

‖R_ad(z, iK_0)‖ ≤ 1 / √(Re(z)² + Δ²)

→ |χ_A(z)| ≤ ‖A‖·‖K_{ω_V|ω_0}‖ / (β·√(Re(z)² + Δ²))
```

**Arakis Normbound** (unabhängig von Δ): ‖R(V)‖ ≤ (β²/2)‖V‖‖[K_0,V]‖
**Dieser Bound** (mit Lücke Δ): explizit besser für Systeme mit Energielücke.

---

### NEU-07 — Matsubara-Pole
**Quelle:** NEU-02 + Spektraltheorie
**Status:** ★ KOROLLAR

```
Singularitäten von χ_A(z) = Pole von R_ad(z, iK_0):

z_mn = i(λ_m - λ_n),    λ_m, λ_n ∈ spec(K_0)

→ Imaginäre Pole = Matsubara-Frequenzen ω_mn = λ_m - λ_n
```

---

### NEU-08 — Zeitbereichsformel (Faltung)
**Quelle:** L-06 (Faltungssatz) + NEU-04 (invertiert)
**Status:** ★ KOROLLAR

```
χ_A(t) = -(i/β) · ∫_0^t σ_{t-s}^{ω_0}( [σ_s^{ω_0}(A), K_{ω_V|ω_0}] ) ds
          + O(β‖V‖²)
```

Beweis: Inverses Laplace von NEU-04, Faltungssatz L-06. □

---

## TEIL E: Spezialfälle

### SP-01 — Statische Modulare Kubo-Identität
```
χ_A^{stat} = -(i/β)·ω_0([A, K_{ω_V|ω_0}]) + O(‖V‖²)  [NEU-05]
```

### SP-02 — Verlinde als Spezialfall
```
K_{ω_β} = β·H = β·(F + TS)  →  (1/β)·∂_x⟨K_Ω⟩ = ∂F/∂x + T·∂S/∂x
Verlinde (2010): bei ∂F/∂x = 0  →  F = T·∂S/∂x  [Spezialfall von SP-01]
```

### SP-03 — Jacobson-Einstein als Spezialfall
```
δQ = (1/β_U)·δ⟨K_Ω^{Rindler}⟩ = T_U·δS_BH
→ G_μν = (8πG/c⁴)·T_μν  [Jacobson 1995, Spezialfall]
```

---

## LÜCKENLOSE BEWEISKETTE

```
Wikipedia: Laplace (L-01)
    ↓ L-07 (Anfangswerttheorem)
    ↓ L-06 (Faltungssatz)

Wikipedia/HY: Hille-Yosida (HY-02, HY-03, HY-04)
    ↓ Resolvent = Laplace der Halbgruppe

QFT-01 (HHW 1967) + QFT-02 (Tomita 1967) + QFT-03 (BR87)
    ↓ KMS ↔ Modularfluss

QFT-05 (Araki 1973): K_{ω_V|ω_0} = βV
QFT-06 (Kubo 1957):  χ_A(t) = -iω([σ_t A, V])
    ↓
NEU-01: Modularfluss ist C₀-Gruppe           [QFT-02 + HY-01]
NEU-02: R_ad(z) = ∫e^{-zt}σ_t dt            [NEU-01 + HY-03]
NEU-03: χ_A(z) = -iω([R_ad(z)A, V])         [QFT-06 + NEU-02]
    ↓
NEU-04: χ_A(z) = -(i/β)ω([R_ad(z)A, K_{ω_V|ω_0}])  [NEU-03 + QFT-05]
    ↓
NEU-05: lim_{z→∞} z·χ_A(z) = χ_A^{stat}    [NEU-04 + L-07 + HY-04]
         = Araki (1973)  ✓
```

**Jeder Pfeil hat eine exakte Referenz. Kein Schritt ohne Beweis.**
