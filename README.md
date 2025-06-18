# 🧠 Buscaminas en Python

Este repositorio contiene una versión básica del juego **Buscaminas** implementada en Python. A continuación se presenta el diagrama de flujo que representa la lógica principal del programa.

## 🔁 Diagrama de Flujo

```mermaid
flowchart TD
    A[Inicio] --> B[Inicializar tablero]
    B --> C[Colocar minas aleatoriamente]
    C --> D[Calcular números adyacentes]
    D --> E[Mostrar tablero]
    E --> F[Pedir entrada al usuario]
    F --> G{¿Es salida?}
    G -- Sí --> H[Terminar juego]
    G -- No --> I{¿Coordenadas válidas?}
    I -- No --> F
    I -- Sí --> J[Revelar celda]
    J --> K{¿Es mina?}
    K -- Sí --> L[Mostrar todas las minas]
    L --> M[Fin del juego - Derrota]
    K -- No --> N{¿Es celda vacía?}
    N -- Sí --> O[Revelar celdas adyacentes]
    O --> P[Mostrar número]
    P --> Q[Verificar victoria]
    Q --> R{¿Completado?}
    R -- Sí --> S[Fin del juego - Victoria]
    R -- No --> F
    N -- No --> P