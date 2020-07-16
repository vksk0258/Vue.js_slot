<template>
  <div class="about">
    <h1>This is an about page</h1>
    <fannaCoder>
      <template v-slot:body>
        <p>body123</p>
      </template>
      <template #header="props">
        <p>head123 {{props.fanna}}</p>
      </template>
      <template v-slot:deafult>
        <p>foot123</p>
      </template>
      <div>
        <h1>hello</h1>
      </div>
    </fannaCoder>
  </div>
</template>
<script>
import fannaCoder from '@/components/fannaCoder.vue';

export default {
  components: {
    fannaCoder
  },
}
</script> 