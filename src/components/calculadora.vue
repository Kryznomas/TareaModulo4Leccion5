<template>
    <div class="calc">
        <h3 class="titulo">Ingrese dos números y seleccione una operación</h3>
        <form class="form">
            <div>
                <input v-model="opa" type="number" class="input-operandoa" id="exampleInputEmail1" aria-describedby="emailHelp" maxlength="8">
            </div>
            <select v-model="operacion" class="select-operacion" name="" id="">
                <option value="+">+</option>
                <option value="-">-</option>
                <option value="*">*</option>
                <option value="/">/</option>
            </select>
            <div class="">
                <input v-model="opb" type="number" class="input-operandob" id="exampleInputPassword1" maxlength="8">
            </div>
            <div class="btns">
              <button @click.prevent="resultadoFinal()" type="submit" class="btn">Calcular</button>
              <button @click.prevent="limpiar()" type="submit" class="btn">Limpiar</button>
          </div>
        </form>
        <div class="display-resultado">
            <h4>Resultado:</h4>
            <p class="display-operandoa">{{opa}}</p>
            <p class="display-operacion">{{operacion}}</p>
            <p class="display-operandob">{{opb}}</p>
            <p class="display-igual">{{igual}}</p>
            <p class="display-total">{{resultado}}</p>
        </div>
    </div>
</template>

<script>
export default {
  name: 'calculadora',
  props: {
    msg: String
  },
  data: function() {
    return {
        opa: "",
        opb: "",
        operacion: "",
        resultado: "",
        igual: "",
        
    }},
    methods: {
        resultadoFinal() {
          
            if (this.resultado == 0){
            switch (this.operacion) {
              case "+":
                this.resultado = parseInt(this.opa) + parseInt(this.opb);
                break;
              case "-":
                this.resultado = parseInt(this.opa) - parseInt(this.opb);
                break;
              case "*":
                this.resultado = parseInt(this.opa) * parseInt(this.opb);
                break;
              case "/":
                this.resultado = parseInt(this.opa) / parseInt(this.opb);
                break;
            }
            }
            else {
              this.resultado = 0;
              switch (this.operacion) {
              case "+":
                this.resultado = parseInt(this.opa) + parseInt(this.opb);
                break;
              case "-":
                this.resultado = parseInt(this.opa) - parseInt(this.opb);
                break;
              case "*":
                this.resultado = parseInt(this.opa) * parseInt(this.opb);
                break;
              case "/":
                this.resultado = parseInt(this.opa) / parseInt(this.opb);
                break;
            }
            }
            this.igual = "="
        },
        limpiar() {
        this.opa= "";
        this.opb= "";
        this.operacion= "";
        this.resultado= "";
        this.igual= "";
        },
    }
}
</script>

<style scoped>
.calc {
  background-color: rgb(202, 202, 202);
  width: 80vw;
  height:40vh;
  padding: 5vw;
  margin-top: 10vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.titulo {
  text-align: center;
}
.form {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  margin-top: 2vw;
  
}
.input-operandoa, .input-operandob {
  margin: 0 1vw 2vw 1vw;
  padding: 2vw;
  font-size: 1rem;
  width: 12vw;
}
.select-operacion {
  padding:0.5vw;
  width: 8vw;
  margin: 0 1vw 2vw 1vw;
}
.display-resultado{
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  margin-top: 2vh;
  width:100%;
}
.display-operandoa, .display-operandob, .display-total{
  margin: 0 0.5vw 0 0.5vw;
  min-width: 3vw;
  max-width: 20vw;
  text-align: left;
  font-size: 1.2rem;
}
.display-operacion, .display-igual{
  margin: 0 0.5vw 0 0.5vw;
  width: 3vw;
  text-align: center;
  font-size: 1.2rem;
}
h3, h4{
  margin: 0 1vw 0 0;
  align-self: center;
}
.btns{
  margin: 0 1vw 2vw 1vw;
}
.btn{
  background-color: rgb(24, 141, 141);
  color: azure;
  margin: 0 1vw 0 1vw;
  height: 100%;
}
</style>
