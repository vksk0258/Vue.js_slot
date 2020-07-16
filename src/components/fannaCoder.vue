<template>
    <div>
        <h1>{{title}}</h1>
        <slot name= "header" :fanna ="fanna"></slot>
        <p> {{ name }} </p>
        <slot name= "body"></slot>
        <slot></slot>
        <button @click="updateName">click</button>
    </div>

</template>

<script>
export default {
    props: {
        title: {
            type: String,
            default : 'default title', //안보내면 보낸다
            required: false // 보내는 조건 설정
        },
        name: { //여기서 name은 부모 컴포넌트에서 보내는 데이터
            type: String,
            default : 'default name', //안보내면 보낸다
            required: false // 보내는 조건 설정
        }
    },
    data() {
        return {
            fanna : 'coder'
            //name : 'fanna' //프롭스랑 같은 이름의 변수를 사용하면 안된다
        }
    },
    methods: {
        updateName() {
            this.name = 'fannaUpdated'; //프롭스 내에서 name을 사용하고 있기 때문에 이렇게 함수 내에서 프롭스에 있는 name을 변경하게 되면 에러가 뜬다
        }
    }
  
}
</script> 

<style scoped>

</style>