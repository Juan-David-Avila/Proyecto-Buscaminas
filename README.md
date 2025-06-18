# Proyecto-Buscaminas

flowchart TD
    A[Inicio del juego] --> B[Llamar función juego()]
    B --> C[Pedir filas, columnas y minas]
    C --> D[Llamar crear_tablero(filas, columnas)]
    D --> E[Llamar colocar_minas(tablero, num_minas)]
    E --> F[Iniciar ciclo while True]
    F --> G[mostrar_tablero(tablero)]
    G --> H[Pedir fila y columna al jugador]
    H --> I[Llamar revelar_celda(tablero, fila, columna)]
    I --> J{¿Es una mina?}
    J -- Sí --> K[Mostrar "Perdiste"]
    K --> L[mostrar_tablero(tablero)]
    L --> M[Fin del juego]
    J -- No --> N{¿Todas celdas sin minas reveladas?}
    N -- Sí --> O[Mostrar "Ganaste"]
    O --> P[mostrar_tablero(tablero)]
    P --> Q[Fin del juego]
    N -- No --> F
