<template>
<div class="title">

<h2>Calculadora IMC</h2>

<div>
  <span id="span1">TopFitness</span>
    <span id="span2">IMC</span>
</div>

</div>
<div id="pagImc">

    <div id="calculator">
        <p>Calcule seu <strong>índice de massa corporal</strong> com nossa calculadora!!</p>
        <form action="/" id="formulario" v-on:submit.prevent="onSubmit">
                    <div class="inputs">
                        <div class="inputs-labels">
                            <label for="peso">Peso (kg): </label>
                            <input type="text" v-model="peso" name="peso" id="peso" placeholder="Ex: 50">
                        </div>
                        <div class="inputs-labels">
                            <label for="altura">Altura (m): </label>
                            <input type="text" v-model="altura" name="altura" id="altura" placeholder="Ex: 1.80">
                        </div>
                    </div>

                    <button id="enviar" @click="enviarForm()" class="botaoAdd"><span id="nameButton">Enviar</span></button>
                    <div id="indication">* Específico Adultos</div>
                    <div id="indication">* Recomendamos sempre contatar um especialista</div>
                    <br/>
            </form>
            <div id="res" ></div>
    </div>

    <div class="responsiveTable">
        <table>
        <caption>Tabela - IMC</caption>
        <thead>  
            <tr>
                <th>Resultado</th>
                <th>IMC</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Abaixo do Peso</td>
                <td> >18,5</td>

            </tr>
            <tr>
                <td>Peso Normal</td>
                <td>18,5 - 24,9</td>

            </tr>
            <tr>
                <td>Sobrepeso</td>
                <td>25 - 29,9</td>

            </tr>
            <tr>
                <td>Obesidade I</td>
                <td>30 - 34,9</td>

            </tr>
            <tr>
                <td>Obesidade II</td>
                <td>35 - 39,5</td>
            </tr>
    </tbody>
</table>

    </div>
</div>
</template>

<script >
    export default {
        name: 'PagImc',
        data(){
            return{
                peso: '',
                altura: '',
                nivelImc: '',
                imc: 0,
                msg: '',
            }
        },
        methods: {
            enviarForm(e){
                
                console.log(this.peso)
                console.log(this.altura)
                
                if (!this.peso) {
                    window.alert('Coloque o "Peso" Corrtamente, EX: 40, 50, 60');
                    return;
                }

                if(this.peso <= 20) {
                    window.alert('Coloque o "Peso" Corrtamente, EX: 1.80 / 1.50 / 1.60');
                    return;
                }

                if (!this.altura) {
                    window.alert('Coloque a "Altura" Corrtamente, EX: 1.80 / 1.50 / 1.60');
                    return;
                }

                if(!this.altura > 3) {
                    window.alert('Coloque a "Altura" Corrtamente, EX: 1.80 / 1.50 / 1.60');
                    return;
                }

                this.imc = this.getImc(this.peso, this.altura)

                this.nivelImc = this.getNivelImc(this.imc);

                console.log(this.nivelImc)

                this.msg = `Seu IMC é ${this.imc} (${this.nivelImc})`;

                this.Resultado(this.msg, true)
                
            },
            getNivelImc(imc) {
                let nivel = ['Abaixo do Peso', 'Peso Normal', 'Sobrepeso', 'Obseidade grau 1', 'Obsedidade grau 2', 'Muito Acima do Peso'];

                if (imc >= 39.9) return nivel[5];
                
                if (imc >= 34.9) return nivel[4];
                
                if (imc >= 29.9) return nivel[3];
                
                if (imc >= 24.9) return nivel[2];
                
                if (imc >= 18.5) return nivel[1];
                
                if (imc < 18.5) return nivel[0];

            },
            getImc(peso, altura) {
                this.imc = peso / altura**2;
                return this.imc.toFixed(2);
            },
            criaP() {
                const paragrafo = document.createElement('p');
                return paragrafo;
            },
            Resultado(msg, isValido) {
                const resultado = document.querySelector('#res');
                resultado.innerHTML = ' ';
                const p = this.criaP();
                if (isValido) {p.classList.add('paragrafo-resultado');
                }   else {
                p.classList.add('bad')
                }
                p.innerHTML = msg;
                resultado.appendChild(p);

            }
        }
        
    }
</script>

<style scoped>

    .title {
        margin: 5rem 0 3rem 0;
    }
    #pagImc{
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: space-evenly;
        flex-flow: row wrap;
        max-width: 75rem;
        margin: 0 auto;
        padding: 2rem;
    }
    /* Form */
    p{
        margin: 2rem 0rem;
        font-size: 1.2rem;
    }

    #formulario {
        display: flex;
        flex-direction: column;
        gap: 0.2rem;
        
    }

    .inputs{
        display: flex;
        flex-direction: row;
        gap: 1.25rem;
    }

    .inputs-labels{
        display: flex;
        flex-direction: column;
        gap: 0.625rem;
    }

    label{
        font-size: 1.1rem;
        font-weight: bold;
    }

    input{
        text-decoration: none;
        border: 0.1rem solid #222;
        padding: 0.8rem;
        margin-bottom: 0.4rem;
        border-radius: 0.875rem;
        font-size: 0.8rem;
    }


    /*BOTAO */
    .botaoAdd{
        background-color: #39B547;
        color:azure;
        border-radius: 1.25rem;
        padding: 0.625rem 0.875rem;
        font-weight: bold;
        display: flex;
        align-items: center;
        justify-content: center;
        position: relative;
        width: 80%;
        margin: 0 auto;
        margin: 0.625rem 0rem;
        cursor: pointer;
    }

    .botaoAdd::before {
    content: "";
    border-radius: 1.25rem;
    background-color: #222;
    position: absolute;
    display: block;
    color: #fff;
    inset: 0;
    z-index: 0;
    transition: transform 300ms ease;
    transform-origin: 100%;
    transform: scaleX(0);

}

#indication {
    color: #39B547;
    font-style: italic;
    margin: 0.188rem;
}

.botaoAdd:hover::before {
    transform: scaleX(1);
    transition-duration: 500ms;
    transform-origin: 0%;
    border-radius: 1.25rem;
    color: white;
}

.botaoAdd:hover{
    color: #fff;
    transition: 0.3s;
    border-radius: 1.25rem;
}

#nameButton{
    z-index: 2;
    background-color: transparent;
    font-size: 1.2rem;
}

/*TABELA */

table {
    width: 100%;
    border-collapse: collapse;
    min-width: 30rem;
    border-radius: 0.625rem;

}

table td, table th {
    border: 0.1rem solid rgb(201, 201, 201);
    padding: 0.5rem;
    text-align: left;
    white-space: nowrap;
}

tfoot td {
    color: #222;
}

thead th {
    color: #222;
}

table caption {
    font-style: italic;
    font-size: 1.6rem;
    text-align: left;
    margin-bottom: 1.6rem;
}

.responsiveTable {
    overflow: hidden;
    overflow-x: auto;
}

@media screen and (max-width: 50rem){

#PagImc {
    padding:2rem 2rem;
    width: auto;
}

table {
    min-width: 22rem;
}

#calculator{
    width: 100%;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    font-size: 1.4rem;

}

input {
    width: 100%;
    font-size: 1.4rem;
}

.botaoAdd {
    width: 100%;
}
}

@media screen and (max-width: 34.375rem) {
    #PagImc {
        padding:4rem 4rem;
    }

    .title {
        margin: auto;
        margin-top: 3rem;
    }
}

@media screen and (max-width: 31.25rem){
    table {
        min-width: 16rem; 
    }

    input {
        font-size: 1.2rem;
    }

}

</style>

    