TicTacToeScenarios Behavior-Driven Developmenet (BDD) practice

1. Inicio el juego:
Como jugador, quiero poder iniciar una nueva partida de Tic-Tac-Toe para poder jugar contra otro jugador.

(BDD)
GIVEN the player is in the title screen and there is no other match already going on
WHEN the player selects the option "New game"
THEN we show the empty grid and the initial turn is assigned to the player


2. Realizar un movimiento:
Como jugador, quiero poder seleccionar una casilla en la cuadrícula para hacer mi movimiento, colocando mi marca ("X" o "O").

(BDD)
GIVEN the player is mid match and it´s the player´s turn
THEN allow the player to choose a square in the grid
WHEN the player chooses the square
THEN draw X or O in that spot

3. Determinacion de ganador:
Como jugador, quiero que el juego determine automáticamente si he ganado, perdido o empatado para saber el resultado de la partida.

(BDD)
GIVEN the player has ended its turn and the other player can't draw in the grid because there is no space
THEN check if there are 3 of the same element in a row
GIVEN it's true
THEN check the player that is related to those marks and show they are the winner


4. Reiniciar el juego:
Como jugador, quiero poder reiniciar el juego para empezar una nueva partida sin tener que recargar la página o aplicación.

(BDD)
GIVEN the player is mid match
THEN if the player wants to restart
WHEN the player clicks on restart
THEN erase the marks already drawn on screen
THEN select a random player to play next


5. Interfaz de usuario(UI) intuitiva
Como jugador, quiero una interfaz de usuario clara y fácil de entender para que pueda jugar sin confusión.

(BDD)
GIVEN the player is in the game
THEN show on screen the Title screen
WHEN the player selects an option in the Title screen
THEN show the new menu related to the option selected

6. Modo de juego multijugador local
Como jugador, quiero poder jugar contra otro jugador en el mismo dispositivo para disfrutar del juego con amigos o familiares.

(BDD)
GIVEN the player is in the title screen
WHEN the player selects local multiplayer
THEN start a match with player 1 and player 2 each assigned a mark
THEN select randomly which player starts


7. Modo de juego contra la Computadora(IA)
Como jugador, quiero poder jugar contra la computadora para practicar y mejorar mis habilidades en Tic-Tac-Toe.

(BDD)
GIVEN the player is in the title screen
WHEN the player selects vs C.P.U.
THEN let the player choose a mark and give the C.P.U. the mark the player didn't choose
THEN start the match with the player starting