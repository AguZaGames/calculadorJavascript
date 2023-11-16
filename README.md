# calculadorJavascript
calculadora creada en JavaScript






const pantalla = document.querySelector(".pantalla");
const botones = document.querySelector(".btn");

botones.forEach(boton => {
    boton.addEventListener("click",() =>{
        const botonApretado = boton.Content;


        if(boton.id === "c"){
            pantalla.textContent ="0";
        } 

        if (boton.id === "borrar"){
            if(pantalla.textContent.length === 1 || pantalla.textContent === "Error") {
            pantalla.textContent = "0";
            } else {
                pantalla.textContent = pantalla.textContent.slice(0, -1);
            }
            return;
        }

        if(boton.id === "igual") {
            try {
            pantalla.textContent = eval(pantalla.textContent);   
            } catch {
            pantalla.textContent = "error!";    
            }
            return;
        }

        if(pantalla.textContent === "0" || pantalla.textContent === "Error") {
        pantalla.textContent = botonApretado;
        } else{
         pantalla.textContent += botonApretado;   
        }
    })
})
