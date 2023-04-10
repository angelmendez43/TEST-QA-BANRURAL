 ========================================   Errores encontrados  ====================================================
- Errorres de sintaxis:
a. en los metodos addeventListener el cual su correcta escritura es la siguente addEventListener.

b. El siguiente error de sintaxis es document.querySelector('lowOrHi'); la cual no la encontraba el programa por estar mal referenciada, la correcion de este error es colocar la referencia correcra que es colocarle un "." document.querySelector('.lowOrHi')

c. en los condicionales if(guessCount === 1), if(userGuess === randomNumber), else if(guessCount === ATTEMPS) encontremos un igual de mas esto ocacionaba que no funcionara los condicionales, se soluciona al quitar el igual de mas

- Errores de logica: 
a. al generar los numeros aleatorios  este nos generar afuera de los numeros enteros positivos la solocion fue colocar la variable aleatoria el rango de numeros solicitado  0 - 100   let randomNumber = Math.floor(Math.random() * (100 - 1) + 1);

b. los intentos permitidos estaban en 5, cuando el programa nos indica que son 10, la solucion es cambiarlo, const ATTEMPS = 10;

c. en el concional donde valuamos si el numero es mayor o menor los textos estan erroneos y la colocacion de las variables estan en la posicion equivocad.
         if(userGuess < randomNumber) {
        lowOrHi.textContent = 'El número es mayor!';
      } else if(userGuess > randomNumber) {
        lowOrHi.textContent = 'El número es menor!';
      }

    solucion 
     if (randomNumber < userGuess) {
        lowOrHi.textContent = 'El número es menor!';
      } else if (randomNumber > userGuess) {
        lowOrHi.textContent = 'El número es mayor!';
      }

d.  en las validaciones de si el usuario gano o perdio se encuentran al reves las validaciones si el usuario encuentra el numero le indicaria que perdio. Tambien vemos que las validaciones de texto estan erroneas, si perdemos no lo coloca en negro y si ganamos nos lo coloca en rojo.
    if(userGuess == randomNumber) {
      lastResult.textContent = '!!!Pérdistes!!!';
      lastResult.style.backgroundColor = 'black';
      lowOrHi.textContent = '';
      setGameOver();
    } else if(guessCount === ATTEMPS) {
      lastResult.textContent = 'Felicitaciones! adivinaste el número!';
      lastResult.style.backgroundColor = 'red';
      setGameOver();
    }

la solocion es colocar las validaciones pertinentes, incluyendo las indicaciones que si ganamos es color verde el mensaje, si perdemos es color rojo
  if (userGuess == randomNumber) {
      lastResult.textContent = 'Felicitaciones! adivinaste el número!';
      lastResult.style.backgroundColor = 'green';
      lowOrHi.style.backgroundColor = 'white';
      lowOrHi.textContent = '';
      setGameOver();
    } else if (guessCount == ATTEMPS) {
      lastResult.textContent = '!!!Pérdiste!!!';
      lastResult.style.backgroundColor = 'red';
      lowOrHi.style.backgroundColor = 'white';
      setGameOver();
    }


-Errores por falta de codigo
a. no tenemos las validaciones de los numeros permitidos a ingresar, esto lo solucionamos creando una variable 
 let restringirNumeros = /^[0-9]+$/;  con la expresion regular que nos indica numeros enteros positivos y sin decimales

creamos los condiciones para validar nuestros numeros permitidos

  if(!userGuess.match(restringirNumeros)){
      alert('No es un numero entero positivo');
      restrigir = false;
    }else if(userGuess < 1 || userGuess > 100){
      alert('El rango de numeros son de 0 a 100');
      restrigir = false;
    }



luego creamos una variable de tipo booleano para validar los numeros permitods
y luego creamos un condicional que si el booleano es diferente no recorra todas las validadciones de si ganos o perdimos para que no lo puera contabilizar como un juego empezado.

