<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> <!--라우터를 사용하고 싶으면 <router-link> 사용-->
      <router-link to="/about">About</router-link>
    </div>
    <!--"/"링크는 home컴포넌트를 가지고 있다
    이때 router-view는 import를 이용해서 home컴포넌트로 바꿔준다
    페이지는 바뀌지만 모든게 index.html안에서 실행된다-->
    <router-view/> 
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
