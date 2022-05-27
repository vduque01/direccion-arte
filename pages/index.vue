<template>
  <CFlex w="100vw" h="100vh" justifyContent="center" alignItems="center"> 
    <CFlex  w="75%" alignItems="center" flexDirection="column">
      <img src="/logo.png" />
      <h1>¿Cuál es el personaje invitado de este mes?</h1>
      <form @submit.prevent="checkContraseña()">
        <input type="text" v-model="valor" />
        <button type="submit">Comprobar</button>
      </form>
      <div class="warning" v-show="showMessage">oh, no :(((( inténtalo de nuevo</div>
    </CFlex>
  </CFlex>
</template>
<script>
export default {
  data() {
    return {
      contraseña: "Rakky Ripper",
      valor: "",
      showMessage: false,
    };
  },
  methods: {
    checkContraseña() {
      const isCorrect = this.contraseña == this.valor;
      if (isCorrect) {
        this.$router.push("/descuento");
      } else {
        this.showMessage = true;
      }
    },
  },
};
</script>

<style>
body{
  background-color: black

}

*{
  color:white;
}



h1{
  font-size: 19px;
  margin-bottom: 16px;
  color: #ff00aa;
  font-weight: bold;
}
img{
  width: 400px;
  padding-bottom: 64px;
}

input{
  background-color: black;
  padding: 16px 32px;
  outline: white 1px solid;
  border-radius: 999px;
}

form{
  display:flex;
  gap: 16px;
}

button{
  background-color: #ff00aa;
  display: flex;
  align-items: center;
  font-weight: bold;
  padding: 16px 32px;
  border-radius: 999px;
  transition: all 0.2s;
}

button:hover{
  background-color: #ff94db;
}

button:active{
  background-color: #800055;
}

.warning{
  font-size: 23px;
  margin-top: 32px;
}
</style>