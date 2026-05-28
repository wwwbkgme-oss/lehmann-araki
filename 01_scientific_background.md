# 1. Wissenschaftliche Ausgangslage

## 1.1 Modular Automorphismen $\sigma_t^\omega$

Die Automorphismengruppe $\sigma_t^\omega$ eines Zustands $\omega$ auf einer von Neumann-Algebra $\mathcal{M}$ wird durch die modulare Funktionalanalyse (Tomita-Takesaki-Theorie) definiert. Für einen Gewicht $\omega$ auf $\mathcal{M}$ mit Reihen $\mathcal{M}_\omega = \mathcal{M} \cap \mathcal{M}'_\omega$ und der Zuordnung
$$ S_\omega: \mathcal{M}_\omega \to \mathcal{M}_\omega^*, \quad \langle S_\omega(x), y \rangle = \omega(yx) $$
existiert für $\phi \in \mathrm{dom}(S_\omega)$ mit $\phi \geq 0$ die modulare Spektralzerlegung $\phi = e^{i\eta}|\phi|$. Dadurch definiert ist die Automorphismengruppe
$$ \sigma_t^\omega(x) = \Delta_\omega^{it} x \Delta_\omega^{-it}, \quad x \in \mathcal{M}, \ t \in \mathbb{R}, $$
wobei $\Delta_\omega$ der modulare Zustandoperator ist.

**Aktueller Stand:** Die Struktur der Gruppe $\sigma_t^\omega$ ist vollständig für Typ-I und Typ-II$_1$ Faktoren bekannt. Bei Typ-III Faktoren ist die Struktur komplexer, insbesondere die Abhängigkeit von der Normalisierung des Gewichts.

## 1.2 Spektraltheorie von $K_0 = -\log \Delta_0$

Sei $(\mathcal{M}, \sigma_t, \omega)$ ein KMS-System mit Gibbs-Operator $\Delta_\omega$. Der Entropieoperator $K_0 = -\log \Delta_\omega$ definiert die modulare Spektralfolge. Die Spektralstruktur von $K_0$ ist entscheidend für das Verständnis der dynamischen Mischung.

**Bekannte Resultate:**
- Für Typ-I Faktoren: Spektrum von $K_0$ ist diskret.
- Für Typ-II$_1$ Faktoren: Spektrum von $K_0$ ist punktweise konvergent.
- Für Typ-III$_1$ Faktoren: $K_0$ hat ein vollständig kontinuierliches Spektrum (Araki, 1972).

## 1.3 Typklassifikation von Faktoren

Die Tomita-Takesaki-Theorie klassifiziert Faktoren in drei Typen:

| Typ | Spektrum von $\Delta_\omega$ | Dynamik |
|-----|------------------------------|---------|
| I$_n$ |punktförmig mit endlich vielen Punkten|trivial|
| I$_{\infty}$ |punktförmig mit unendlich vielen Punkten|trivial|
| II$_1$ |ein Punkt ($\sigma_t = \mathrm{id}$)| stationär|
| II$_\infty$ |ein Punkt mit nicht-trivialer Automorphismie| stationär|
| III$_1$ |vollständig kontinuierlich| nicht-ergodisch|
| III$_\lambda$ |$\{0, 1\} \cup (0, \infty)$ für $\lambda \in (0,1)$| Teilergodisch|

## 1.4 Ergodische Eigenschaften in AQFT

In der Algebraische Quantenfieldentheorie (AQFT) werden von Neumann-Algebren $\mathcal{M}_\mathcal{O}$ den Lorentz-Ebene $L_\mathcal{O}$ zugeordnet. Die modulare Dynamik $\sigma_t^{\omega_\mathcal{O}}$ an den Ebenen ist für die Untersuchung von Thermalisierung und Entropie entscheidend.

**Aktueller Stand:** Für Typ-III$_1$ Systeme ist bekannt, dass die ergodische Eigenschaft
$$ \lim_{t \to \infty} \|\sigma_t^\omega(A) - \omega(A)\|_2 = 0 $$
für alle $A \in \mathcal{M}$ erfüllt ist (Araki, 1972). Die stärkere Form der Ergeodigkeit mit Quantifizierung ist jedoch offen.

## 1.5 Referenzen

- Takesaki, M.: *Theory of Operator Algebras I*, Springer (1979)
- Connes, A.: *Noncommutative Harmonic Analysis*, Springer (1979)
- Araki, H.: *Modular Theory and KMS Condition*, Lectures in Pure Math. 136 (1988)