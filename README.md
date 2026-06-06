[README.md](https://github.com/user-attachments/files/28657323/README.md)

# Series-de-Tiempo

Repositorio de código para los cursos de **Cálculo Estocástico** y **Series de Tiempo**.

---

## Estructura

```
Series-de-Tiempo/
├── Codigo.py            ← Motor principal del Proyecto Final (Labs 1–5 + Proyecto 6)
├── seriesdetiempo.py    ← Modelo SARIMA(0,1,1)(0,1,1)₁₂ sobre AirPassengers
├── donsker.jsx          ← Visualización interactiva del Teorema de Donsker (React)
└── levy_area_Z2.gif     ← Animación del Área de Lévy
```

---

## Archivos

### `Codigo.py` — Motor del Proyecto Final de Cálculo Estocástico

Genera datos sintéticos calibrados a parámetros de AAPL, ejecuta cinco laboratorios y exporta figuras en PDF y un archivo `results.json` con resultados numéricos.

| Lab | Tema | Método |
|-----|------|--------|
| 1 | Estimación de un MBG con datos de una acción | MLE + Monte Carlo |
| 2 | Volatilidad realizada y ventanas móviles | Desv. estándar móvil anualizada |
| 3 | Opciones europeas vanilla | Monte Carlo + Black-Scholes |
| 4 | Opciones americanas (put) | Árbol binomial |
| 5 | Opciones parisinas down-and-out | Monte Carlo con reloj de permanencia |
| Proyecto 6 | Superficie de precio parisino V(H,D) | Monte Carlo, heatmap H × D |

**Dependencias:**
```bash
pip install numpy pandas matplotlib scipy
# Opcional para datos reales:
pip install yfinance
```

**Ejecución:**
```bash
python Codigo.py
```

---

### `seriesdetiempo.py` — Modelo SARIMA sobre AirPassengers

Ajusta un modelo **SARIMA(0,1,1)(0,1,1)₁₂** al dataset clásico AirPassengers (1949–1960). Incluye respaldo con datos sintéticos si no hay conexión a internet.

**Dependencias:**
```bash
pip install pandas matplotlib statsmodels
```

**Ejecución:**
```bash
python seriesdetiempo.py
```

---

### `donsker.jsx` — Visualización del Teorema de Donsker

Componente React que ilustra la convergencia en distribución:

$$W_n(t) = \frac{S_{\lfloor nt \rfloor}}{\sqrt{n}} \xrightarrow{d} B(t) \quad n \to \infty$$

donde $S_k = \xi_1 + \cdots + \xi_k$ es una caminata aleatoria con $\xi_i \in \{-1,+1\}$ equiprobables y $B(t)$ es el movimiento browniano estándar.

Funcionalidades: animación con control de velocidad, selector de $n \in \{100, 500, 1000, 5000\}$, generación de nuevas muestras y rastros de trayectorias anteriores.

---

### `levy_area_Z2.gif` — Animación del Área de Lévy

Animación generada con `matplotlib` que ilustra el Área de Lévy de un proceso estocástico bidimensional.

---

## Reproducibilidad

- `Codigo.py` usa semilla fija (`seed=20260526`) para resultados idénticos en cada ejecución.
- `seriesdetiempo.py` incluye datos sintéticos de respaldo si no hay internet.
- Los PDFs de entrega y datos pesados **no están en este repositorio** — residen en Google Drive.

---

## Curso

| | |
|---|---|
| Universidad | Universidad Panamericana |
| Cursos | Cálculo Estocástico · Series de Tiempo |
| Año | 2026 |
