<template>
  <div id="app">
    <form>
      <div class="row">
        <label>Título: </label>
        <input v-model="titulo" />
      </div>

      <div class="row">
        <label>Emoji: </label>
        <select v-model="emoji">
          <option value="👩🏻‍💻">👩🏻‍💻</option>
          <option value="🧑🏻‍💻">🧑🏻‍💻</option>
        </select>
      </div>

      <div class="row">
        <label>Apreciación: </label>
        <input type="radio" value="Regular" name="apreciacion" v-model="apreciacion" />Regular
        <input type="radio" value="Bien" name="apreciacion" v-model="apreciacion" />Bien
        <input type="radio" value="Muy Bien" name="apreciacion" v-model="apreciacion" />Muy Bien
        <input type="radio" value="Increíble" name="apreciacion" v-model="apreciacion" />Increíble
      </div>

      <div class="row">
        <label>Competencias aprendidas: </label>
        <div class="input-group">
          <div class="input-option"><input name="competencias" v-model="competencias" type="checkbox"
              value="Morfología de un componente" />Morfología de un componente</div>
          <div class="input-option"> <input name="competencias" v-model="competencias" type="checkbox"
              value="One-Way y Two-Way data binding" />One-Way y Two-Way data binding</div>
          <div class="input-option"> <input name="competencias" v-model="competencias" type="checkbox"
              value="El patrón de diseño MVVM" />El
            patrónde diseño MVVM</div>
          <div class="input-option">
            <input name="competencias" v-model="competencias" type="checkbox" value="Directivas" />Directivas
          </div>
          <div class="input-option"><input name="competencias" v-model="competencias" type="checkbox"
              value="Estado" />Estado</div>
        </div>
      </div>

      <div class="row">
        <label>Opinión: </label>
        <textarea v-model="opinion" rows="2"></textarea>
      </div>
    </form>

    <div class="documento">
      <p class="emoji">{{ emoji }}</p>
      <h1>{{ titulo }}</h1>
      <h2>Y me parece {{ apreciacion }}</h2>
      <h3>He aprendido:</h3>
      <p>{{ competencias }}</p>
      <h4>Mi opinión hasta ahora del framework es:</h4>
      <p>{{ opinion }}</p>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {
  },
  data() {
    return {
      titulo: "",
      emoji: "",
      apreciacion: "",
      competencias: [],
      opinion: ""
    }
  }
}
</script>

<style>
* {
  margin: 0;
}

body {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  font-size: 14px;
  font-family: sans-serif;
}

#app {
  display: flex;
  gap: 40px;
}

form {
  background: #333;
  color: #cecece;
  display: flex;
  flex-direction: column;
  padding: 1.5rem;
  border-radius: 1.5rem;

}

form .row {
  display: flex;
  align-items: start;
  justify-content: start;
  gap: 5px;
  padding: 1rem 0;
  border-bottom: 1px solid #cecece;
}

form div label {
  text-align: left;
}

form .input-group {
  display: flex;
  flex-direction: column;
  gap: 5px;
}

form .input-option {
  display: flex;
  align-items: center;
  gap: 5px;

}

form textarea {
  width: 80%;
  padding: 0.5rem;
  border-radius: 0.5rem;
}

.documento {
  background: white;
  color: black;
  width: 800px;
  padding: 1.5rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border: 1px solid black;
  border-radius: 1.5rem;
  gap:1rem;
}

.documento .emoji {
  font-size: 50px;
}
</style>
