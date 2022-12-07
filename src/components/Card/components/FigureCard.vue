<template>
    <figure>
        <img :src="imgUrl" :alt="imgAlt">
        <figcaption>{{ imgCaption }}</figcaption>
    </figure>
</template>

<script>
export default {
    props: {
        imgUrl: String,
        imgCaption: String,
        imgAlt: String,
    }
}
</script>

<style>

</style>