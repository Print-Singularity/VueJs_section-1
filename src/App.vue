<!-- eslint-disable vue/require-v-for-key -->
<template>
  <section>
    <img :src="picture" :width=size :heigth=size ref="imageURL">
    <br>




  <h1>ชื่อ-นามสกุล : {{ getFullName }}</h1>
  <h1>อายุ : {{age}}</h1>
  {{ isVisible }}
  <button @click="showData()">{{isVisible ? 'hide ' : 'show '}}data</button>
  <article v-show="isVisible">
    <p>ที่อยู่ : <span v-html="address"></span></p>
    <a :href="social">Facebook</a>
    <p v-if="hobby.length ===0">No hobby</p>
    <div v-else>
      <p>Hobby</p>
      <ul>
        
        <li v-for="(value,key) in hobby" :key="key">
        {{ value }}
        </li>
      </ul>
    </div>
    <p>ข้อมูลพื้นฐาน</p>
    <ul>
      <li v-for="(item,key) in general" :key="key">{{ key }}  {{ item }}</li>
    </ul>
  </article>
  <p>Metthod 1 : {{ getRandomBymethod() }}</p>
  <p>Metthod 2 : {{ getRandomBymethod() }}</p>
  <p>Metthod 3 : {{ getRandomBymethod() }}</p><br>
  <p>Computed 1 : {{ getRandomBycomput }}</p>
  <p>Computed 3 : {{ getRandomBycomput }}</p>
  <p>Computed 3 : {{ getRandomBycomput }}</p>
  
  </section>
</template>

<script>


export default {
  name : 'App',
  data(){
    return{
      firstName:'Sutad',
      lastNmae:'Rungsrirat',
      age:27,
      address:'<strong>กรุงเทพ<strong>',
      picture:"https://cdn-icons-png.flaticon.com/512/3674/3674599.png",
      size: 150,
      social:"https://www.facebook.com/keroro.kobsutad",
      hobby:["game",'music','run','movie'],
      nickname:'',
      general:{
        sex:'male',
        weight:'61',
        heigth:'174',
        
      },
      isVisible: false
    }
  },
  methods:{
    showData(){
      this.isVisible =! this.isVisible
    },
    getRandomBymethod(){
      return Math.random()
    }
  },
  computed:{
    getFullName(){
      return this.firstName +" "+ this.lastNmae

    },
    getRandomBycomput(){
      return Math.random()
    }
  }
  
}
</script>

<style>

</style>
