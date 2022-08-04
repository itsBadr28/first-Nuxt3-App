<script setup lang="ts">
import { Gender, Popularity, Length } from '@/data.js';



interface OptionProps {
    option: {
        title: string;
        category: string;
        buttons: Gender | Popularity | Length;
    };
    options: {
        gender: Gender,
        popularity: Popularity,
        length: Length,
    }
}

const props = defineProps<OptionProps>();

</script>
<template>
<div class="options-container">
      <div class="option-container">
        <h4>{{option.title}}</h4>
        <div class="option-button">
          <button v-for="value in option.buttons" :key="value" @click="options[option.category] = value" :class=" options[option.category] === value && 'option-active' " class="btn">
          {{value}}
          </button>
          
        </div>
    
    </div>
</div>
</template>