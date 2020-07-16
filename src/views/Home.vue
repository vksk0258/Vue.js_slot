<template>
  <div>
    <h1>This is Home page</h1>
    <!-- <form action =""> -->
      <!-- 컴포넌트에도 v-model을 사용이가능해서 사용하면 name이 아니라 value를 보낸다 -->
      <inputField v-model="name" /><!--자식에 있는 데이터를 가져올때-->
      <button @click="updateName">Submit</button>
    <!-- </form> -->
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
      name : 'fanna'
    }
  },

  beforeCreate() {
    console.log('beforeCreate', this.name); //befoeCreate에서는 name의 접근이 불가능하다
  },

  created() {
    console.log('created', this.name); //여기서부터 콘솔로그에 뜨면서 데이터의 접근이 가능해진다, 보통 여기서 서버의 요첨을 많이 보낸다
  },

  beforeMount() { // 마운트가 되기전 app이 실행이 되기 전
    alert('beforeMount');
  },

  mounted() {  // 마운트가 되면 app이 실행되어진다, dom에 접근 가능 dom컨트롤은 mounted에서 한다
    alert('Mounted');
  },

  beforeUpdate() { //데이터가 바뀌기 전에 beforeUpdater 실행된다
    alert('beforeUpdate');
  },

  updated() { //데이터가 업데이트 되면서 실행된다
    alert('updated');
  },

  beforeDestroy() { //페이지가 넘어갈때 전에 컴포넌트는 없어지고 넘어가는 컴포넌트가 들어온다 여기서는 메모리 누수를 방지하기 위해 이벤트 리스너가 있으면 삭제해준다 데이터를 초기화 해준다는 등
    alert('beforeDestroy')
  },

  destroyed() {
    alert('destroyed')
  },
  methods: {
    updateName() { //함수가 실행되면 화면이 새로고침 되면서 인스턴스가 다시 시작하는데 이때 마운트가 실행된다
      this.name = 'hello';
    }
//     updateName(name) { //여기 name안에 넘겨받은 벨류가 들어간다 
//       this.name = name;
//     }
//   }
}
}

  

</script>

<style scoped>
h1 {
  color : red;
}
</style>