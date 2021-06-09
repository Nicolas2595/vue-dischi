<template>
<div class="template">
    <img :src="item.poster">
    <h3>{{item.title}}</h3>
    <p>{{ item.author }}</p>
    <div>{{ item.year }}</div>
</div>
</template>

<script>
export default {
    name: "Covers",
    props: ["item"]
}
</script>

<style lang="scss" scoped>

    .template {

        background-color: #2e3a46;

        img {
            height: 120px;
            padding-top: 10px;
        }
    }

    h3 {
        color: white;
        font-size: 18px;
        text-align: center;
        padding-top: 20px;
    }

    p {
        color: lightgray;
        text-align: center;
        margin-bottom: 0;
        padding-top: 5px;
    }

    div {
        color: lightgray;
        text-align: center;
        padding-bottom: 5px;
    }

</style>