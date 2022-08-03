<script setup>
  const options = reactive({
    gender: "Girl",
    popularity: "Unique",
    length: "Short",
  })  
</script>

<template>
  <div class="container">
    <h1>Baby Name Genertor</h1>
    <p>Choose your options and click the "Find Name" Button below</p>
    <div class="options-container">
      <div class="option-container">
        <h4>1) Choose a gender</h4>
        <div class="option-button">
          <button @click="options.gender = 'Boy' " :class=" options.gender === 'Boy' && 'option-active' " class="btn">Boy</button>
          <button @click="options.gender = 'Unisex' " :class=" options.gender === 'Unisex' && 'option-active' " class="btn">Unisex</button>
          <button @click="options.gender = 'Girl' " :class=" options.gender === 'Girl' && 'option-active' " class="btn" >Girl</button>
        </div>
      </div>
      <div class="option-container">
        <h4>2) Choose a name's popularity</h4>
        <div class="option-button">
          <button  @click="options.popularity = 'Thendy' " :class=" options.popularity === 'Thendy' && 'option-active' " class="btn">Thendy</button>
          <button  @click="options.popularity = 'Unique' " :class=" options.popularity === 'Unique' && 'option-active' " class="btn">Unique</button>
        </div>
      </div>
      <div class="option-container">
        <h4>1) Choose name length</h4>
        <div class="option-button">
          <button @click="options.length = 'All' " :class=" options.length === 'All' && 'option-active' " class="btn">All</button>
          <button @click="options.length = 'Long' " :class=" options.length === 'Long' && 'option-active' " class="btn">Long</button>
          <button @click="options.length = 'Short' " :class=" options.length === 'Short' && 'option-active' " class="btn">Short</button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  width: 50%;
  height: 760px;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  margin: auto;
  margin-bottom: auto;
  margin-top: auto;
  background-color: #ffafcc;
  border-radius: 10px;
}
.container h1 {
  font-size: 2.5rem;
  color: #3c0b5c;
  text-align: center;
  font-weight: bold;
  margin-bottom: 1rem;
}
h4 {
  font-size: 1.5rem;
  color: #3c0b5c;
  text-align: center;
  font-weight: bold;
  margin-bottom: 1rem;
}
.container p {
  font-size: 1.5rem;
  color: #3c0b5c;
  text-align: center;
  margin-bottom: 1rem;
}
.options-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 100%;
}
.option-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 100%;
}
.option-button {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  width: 100%;
  color: #3c0b5c;
}
.btn {
  margin: 10px;
  padding: 10px;
  border: 1px solid #3c0b5c;
  border-radius: 5px;
  background-color: white;
  color: #3c0b5c;
  font-size: 1.2rem;
  font-weight: bold;
  cursor: pointer;
}
.btn:hover {
  background-color: #3c0b5c;
  color: white;
}
.option-active {
  background-color: #14792a;
  color: white;
}

</style>

