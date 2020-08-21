<template>
  <div>
    <input type="text" v-model="newtodo">
    <button @click="addnewtodo">add new task</button>

    <ul>
      <li v-for="(task, index) in todolist" :key="index++" class="noDots">
        {{index}}. {{task}} 
        <button @click="removetodo">remove</button>
      </li>  
    </ul>
  </div>
</template>

<script>
export default {
  name: 'App',
  data(){
    return {
      todolist: [],
      newtodo: ' ',
    }
  },


  methods: {
    addnewtodo() {
      this.todolist.push(this.newtodo);
    },

    removetodo(){
      this.todolist.splice(this.index, 1)
    }
  }
}
</script>

<style>
  .centerAligned{
    text-align: center;

  }
  .noDots{
    list-style-type: none;
  }
</style>

//  Створити простий todolist В папці assests є скрін як приблизно має виглядати Має бути масив тудушок, 
//  в інпуті вписуємо туду і пушимо в масив за допомогою кнопки Add. 
//  Видаляємо тудушки за допомогою кнопки delete. Якщо тудушок більше 10 кнопка повинна сховатись.