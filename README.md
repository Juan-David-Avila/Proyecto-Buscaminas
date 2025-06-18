# Proyecto-Buscaminas


flowchart TD
    Start([Inicio del juego])
    Start --> Juego[Llamar función juego()]
    Juego --> Input[Solicitar filas, columnas y minas]
    Input --> CrearTablero[Llamar crear_tablero()]
    CrearTablero --> ColocarMinas[Llamar colocar_minas()]
    ColocarMinas --> CicloWhile[Inicio ciclo while True]
    
    CicloWhile --> MostrarTablero[Llamar mostrar_tablero()]
    MostrarTablero --> PedirJugada[Pedir fila y columna al jugador]
    PedirJugada --> Revelar[Llamar revelar_celda()]
    
    Revelar --> EsMina{¿La celda tiene mina?}
    EsMina -- Sí --> Perdiste[Mostrar "¡Perdiste!"]
    Perdiste --> MostrarFinal[Mostrar tablero completo]
    MostrarFinal --> FinPerder([Fin del juego])
    
    EsMina -- No --> VerificarGanador{¿Todas las celdas sin minas fueron reveladas?}
    VerificarGanador -- Sí --> Ganaste[Mostrar "¡Ganaste!"]
    Ganaste --> MostrarFinalGanador[Mostrar tablero completo]
    MostrarFinalGanador --> FinGanar([Fin del juego])
    
    VerificarGanador -- No --> CicloWhile