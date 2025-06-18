# Proyecto-Buscaminas


flowchart TD
    Start([Inicio del juego])
    Start --> Juego[Llamar función juego()]
    Juego --> Input[Solicitar filas, columnas y minas]
    Input --> CrearTablero[Llamar crear_tablero()]
    CrearTablero --> ColocarMinas[Llamar colocar_minas()]
    ColocarMinas --> CicloWhile[Inicio del ciclo while True]

    CicloWhile --> MostrarTablero[Mostrar tablero oculto]
    MostrarTablero --> PedirJugada[Pedir fila y columna al jugador]
    PedirJugada --> Revelar[Llamar revelar_celda()]
    Revelar --> EsMina{¿Es una mina?}

    EsMina -- Sí --> Perdiste[Mostrar "¡Perdiste!"]
    Perdiste --> MostrarFinal[Mostrar tablero completo]
    MostrarFinal --> FinPerdiste([Fin del juego])

    EsMina -- No --> VerificarGanador{¿Todas las celdas sin mina están reveladas?}
    VerificarGanador -- Sí --> Ganaste[Mostrar "¡Ganaste!"]
    Ganaste --> MostrarFinalGana[Mostrar tablero completo]
    MostrarFinalGana --> FinGana([Fin del juego])

    VerificarGanador -- No --> CicloWhile
