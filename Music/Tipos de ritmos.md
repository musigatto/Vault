---

---
![0. Navigation](0.%20Navigation.md)

| Modo rítmico | Patrón de duración | Esquema |
|---|---|---|
| Troqueo | Larga – breve | — ⏑ |
| Yambo | Breve – larga | ⏑ — |
| Dáctilo | Larga – breve – breve | — ⏑ ⏑ |
| Anapesto | Breve – breve – larga | ⏑ ⏑ — |
| Espondeo | Larga – larga | — — |
| Tribraquio | Breve – breve – breve | ⏑ ⏑ ⏑ |

![](attachments/image.png)

![](attachments/image%201.png)
```lilypond
 \version "2.24.0"
\language "español"

\header {
  title = "Columna 1"
  subtitle = "Transcripción rítmica"
  tagline = ##f
}

\relative c' {
  \time 4/4
  \tempo 4 = 80

  % Fila 1: 1 línea vertical -> Negra
  c4 |

  % Fila 2: 3 líneas verticales, número 3 -> Tresillo de corcheas
  \tuplet 3/2 { c8 c8 c8 } |

  % Fila 3: 2 líneas verticales, 2 puntos -> Dos corcheas staccato
  c8-. c8-. |

  % Fila 4: 2 líneas verticales, 2 puntos -> Dos corcheas staccato
  c8-. c8-. |

  % Fila 5 (patrón inferior): Silencio (7) + Nota (丿)
  % Interpretado como silencio de negra + negra
  r4 c4 |
}
```
