<template>
  <section>
    <img :src="image" :width="size" :height="size" />
    <br />
    <form @submit.prevent="submitForm">
      <label>ป้อนชื่อเล่น</label>
      <input type="text" ref="nicnNmeEl" />
      <button type="submit">Save</button>
    </form>
    <h1>{{ getFullName }}</h1>
    <h2>{{ lastName }}</h2>
    <h2>{{ nicname }}</h2>
    <h2>เงินเดือน :{{ salary }}</h2>
    <h2>ตำแหน่ง :{{ getPosition }}</h2>
    <button @click="addSalary">เพิ่มเงินเดือน</button>
    {{ isVisible?"ซ่อน":"แสดง" }}
    <button @click="toggleVisible">รายละเอียด</button>
    <article v-show="isVisible">
      <p>{{ age }}</p>
      <span v-html="address"></span>
      <p v-if="artist.length === 0">ไม่มีข้อมูล</p>
      <div v-else>
        <ul>
          <li v-for="(item, index) in artist" :key="index">{{ item }}</li>
        </ul>
      </div>
    </article>
  </section>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      firstName: "Chisato",
      lastName: "Nishikigi",
      nicname: "",
      age: 17,
      address: "<strong>School</strong>",
      image:
        "https://i.pinimg.com/736x/6c/1c/fb/6c1cfb3af6cd4ce1aef84096160a309d.jpg",
      size: 150,
      artist: [
        "BTS",
        "Twice",
        "Official Hige Dandism",
        "Yoasobi",
        "Yonezu Kenshi",
      ],
      isVisible:false,
      salary:20000,
    };
  },
  methods: {
    submitForm() {
      this.nicname = this.$refs.nicnNmeEl.value;
    },
    toggleVisible(){
      this.isVisible=!this.isVisible
    },
    addSalary(){
      this,this.salary+=5000
    }
  },
  computed:{
      getFullName() {
        return `${this.firstName + " " + this.lastName}`;
      },
      getPosition(){
        return this.salary>=35000?"Project Manager":"Programmer"
      }
  },
  watch:{
    salary(value){
      if(value>50000){
        alert("เงินเดือนไม่ควรเกิน 50,000 บาท")
        setTimeout(()=>{
          this.salary=20000
        },2000)
      }
    }
  }
};
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
