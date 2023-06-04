<template>
  <section>
      <img :src="image" :width="size" :height="size"/>
      <br/>
      <form @submit.prevent="submitForm">
          <label>ป้อนชื่อเล่น</label>
          <input type="text" ref="nicnNmeEl"/>
          <button type="submit">Save</button>
      </form>
      <h1>{{ getFullName() }}</h1>
      <h2>{{ lastName}}</h2>
      <h2>{{ nicname }}</h2>
      <p>{{ age }}</p>
      <span v-html="address"></span>
      <button v-on:click="clickButton">Click</button>
      <button @click="increament">+</button>
      <button @click="decrement">-</button>
  </section>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    return{
      firstName:"Chisato",
      lastName:"Nishikigi",
      nicname:"",
      age:17,
      address:"<strong>School</strong>",
      image:"https://i.pinimg.com/736x/6c/1c/fb/6c1cfb3af6cd4ce1aef84096160a309d.jpg",
      size:150,
    }
  },
  methods:{
    getFullName(){
      return `${this.firstName+" "+this.lastName}`
    },
    clickButton(){
      alert(this.firstName)
    },
    increament(){
      this.age++
    },
    decrement(){
      this.age--
    },
    submitForm(){
      this.nicname=this.$refs.nicnNmeEl.value
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
