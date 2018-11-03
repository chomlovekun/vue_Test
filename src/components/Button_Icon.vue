<template>
    <div>
        <button type="button" @click="SendText()" class="btn btn-info">
            <span :class="icon">{{ name }}</span>
        </button>

    </div>
</template>

<script>
    export default {
        props:{
            icon :{
                type : String,
                default : "fa fa-search"
            },
            name :{
                type : String,
                default : "Hello World"
            } 
        },
        methods:{
            SendText(){
                this.$emit('buttonText',name)
            }
        }
    }
</script>

<style scoped >

</style>