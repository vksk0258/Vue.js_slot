<template>
  <div>
    <h1>This is Home page</h1>
    <form action ="">
      <!-- 컴포넌트에도 v-model을 사용이가능해서 사용하면 name이 아니라 value를 보낸다 -->
      <inputField v-model="name" /><!--자식에 있는 데이터를 가져올때-->
      <button>Submit</button>
    </form>
    {{name}}
   
  </div>
</template>

<script>
import inputField from '@/components/inputField.vue';
export default { //데이터는 펑션으로 사용
components:{
  inputField
},
  data() {
    return {
      name : ''
    }
  },
  // methods: {
  //   // updateName(name) { //여기 name안에 넘겨받은 벨류가 들어간다 
  //   //   this.name = name;
  //   // }
  // }
}
</script>

<style scoped>
h1 {
  color : red;
}
</style>