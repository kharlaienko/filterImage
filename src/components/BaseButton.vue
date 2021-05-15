<template>
    <button @click.stop="toogleIsActive" type="button" :class="{active : isActive}">
        {{ btnText }}
    </button>
</template>

<script>
export default {
    props:{
        btnText: String,
    },

    data(){
        return{
            isActive: false
        }
    },

    methods: {
        toogleIsActive(){
            this.isActive ? this.isActive = false : this.isActive = true;
        }
    }
}
</script>

<style scoped>
.active{
    background-color: red;
}
</style>