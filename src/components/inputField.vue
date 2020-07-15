<template>
    <div>
        <label for=""> NAME </label>
        <input
            type='text'
            :value='value'
            style='padding: 30px; border: 2px solid green;'
            @input="$emit('input', $event.target.value)"
        >
        <!-- @input 값을 입력할때마다 발생하는 이벤트 컴포넌트 -->
    </div>
</template>

<script>
export default {
    props: {
        value: {
            type: String,
            required: true
        }
    },
    // methods: {
    //     updateName(e) {
    //         console.log(e.target.value);
    //         this.$emit('update-name',e.target.value);//위에 벨류를 부모컴포넌트로 올리는 방법
    //     }
    // }
}
</script>