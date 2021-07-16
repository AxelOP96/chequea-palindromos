# chequea-palindromos
App que chequea si una palabra es un palindromo
 
 *Funciones*

 Primero selecciono los elementos del html que van a interactuar con JavaScript y utilizo sus clases y las convierto en constantes de JavaScript, para poder utilizarlas mas adelante.

const btn = document.querySelector(".btn");
const result = document.querySelector(".result");

Creo un escucha eventos que al hacer click llama a la funcion palindrome.
btn.addEventListener("click", palindrome);

Creo la funcion palindrome que selecciona la palabra que se pone en el elemento input, convierte la longitud de su palabra en un variable. y se crean 2 variables una de inicio y una de fin para compararlas y asi chequear si efectivamente la palabra ingresada es un palindromo.
function palindrome() {
    const word = document.querySelector(".input-text").value;
    let len = word.length;

    let start = word.substring(0, Math.floor(len / 2)).toLowerCase();
    let end = word.substring(len - Math.floor(len / 2)).toLowerCase();

    //let flip = end.split("").reverse().join("");
    let flip = [...end].reverse().join("");
    if(start == flip) {
        result.innerHTML = `${word.toUppercase()} is a palindrome`;
    } else {
        result.innerHTML = `${word.toUppercase()} is not a palindrome`;
    }
    //alert(flip);
}