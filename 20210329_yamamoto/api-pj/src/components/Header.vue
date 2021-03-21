<template>
    <div id="Header">
        <input type="text" v-model="fisPostCode">
        <button @click="address">住所自動入力</button>
        <p>Address:{{address}}</p>
    </div>
</template>

<script>
export default{
    data(){
        return{
            text:""
        };
    },
    methods:{
        address(){
            this.$emit("gettext",this.text);
        }
    }
};
</script>
