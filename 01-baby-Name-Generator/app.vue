<script setup lang="ts">
import {Gender, Popularity, Length, names} from "@/data"


  interface OptionsState {
    gender: Gender;
    popularity: Popularity;
    length: Length;
  }
  
  const options: OptionsState = reactive({
    gender: Gender.BOY,
    popularity: Popularity.TRENDY,
    length: Length.ALL,
  })  

  const computeSelectedName = ( ) => {
    const filterName = names
    .filter((name) => name.gender === options.gender )
    .filter((name) => name.popularity === options.popularity )
    .filter((name) => {
      if (options.length === Length.ALL){
        return true
      } else {
        return name.length === options.length
      }
    })

    selectedNames.value = filterName.map((name) => name.name)
  }

  const selectedNames = ref<string[]>([])

  const optionsArray = [
  {
    title: "1) Choose a gender",
    category: "gender",
    buttons: [Gender.GIRL, Gender.UNISEX, Gender.BOY],
  },
  {
    title: "2) Choose the name's popularity",
    category: "popularity",
    buttons: [Popularity.TRENDY, Popularity.UNIQUE],
  },
  {
    title: "3) Choose name's length",
    category: "length",
    buttons: [Length.SHORT, Length.ALL, Length.LONG],
  },
];
</script>

<template>
  <div class="container">
    <h1>Baby Name Genertor</h1>
    <p>Choose your options and click the "Find Name" Button below</p>
    <div class="options-container">
      <Option
        v-for="option in optionsArray"
        :key="option.title"
        :option="option"
        :options="options"
      />
      <div>
        <button class="primary" @click="computeSelectedName"> Find Name</button>
      </div>
    </div>
    <div>
      <div v-for=" name in selectedNames" :key="name.id" >
      
      {{ name }} <span> X </span> 
      </div>
    </div>
  </div>
</template>

<style >
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
.primary {
  background-color: #14792a;
  color: white;
  border-radius: 6.5rem;
  padding: 10px;
  border: none;
}

</style>

