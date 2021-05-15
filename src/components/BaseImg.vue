<template>
<div :style="sizeForImgBox" class="centered bg">
    <img v-show="isImageShow" ref="image" :src="imgSrc"/>
    <p v-if="!isImageShow">нет здесь картинки</p>
</div>
</template>

<script>
export default {
    props: {
        imgSrc: String,
    },

    data(){
        return {
            isImageShow: true,
        }
    },

    computed: {
        rightWidth(){
            return this.$attrs.width !== 0 ? this.$attrs.height : `300px`
        },

        rightHeight(){
            return this.$attrs.height !== 0 ? this.$attrs.height : `300px`
        },

        sizeForImgBox(){
            return `height: ${this.rightHeight}; width: ${this.rightWidth}`
        }
    },

    methods: {
        loadImageSrc(){
            const img = this.$refs.image;
            img.onload = (event) => {
                event.target.style.width = this.rightWidth
                event.target.style.height = this.rightHeight
            }
        },
    },

    mounted() {
        this.loadImageSrc();
    }
}
</script>

<style scoped>
.centered{
    margin-inline: auto;
}

.bg{
    background-color: #ccc;
}
</style>