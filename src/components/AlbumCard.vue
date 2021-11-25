<template>
            <div class="card d-flex flex-column align-items-center">
                <img :src="Image" :alt="MainTitle">
                <h3>{{ MainTitle }}</h3>
                <h5>{{ Author }}</h5>
                <span>{{ Text1 }}</span>
                <span>{{ Text2 }}</span>
            </div>
</template>

<script>
export default {
    name: 'AlbumCard',

    props: {
        Image: String,
        MainTitle: String,
        Author: String,
        Text1: String,
        Text2: String,
    },

}
</script>

<style scoped lang="scss">
    .card {
        padding: 10px;
        background: #2e3a46;
        color: #fff;
        text-align: center;
        border-radius: 0;

        img {
            width: 100%;
            aspect-ratio: 1 / 1;
        }

        h3 {
            padding: 15px 0 8px;
            font-size: 16px;
            text-transform: uppercase;
        }

        h5,
        span {
            font-size: 12px;
            color: #717377;
            font-weight: 600;
        }

        span:last-child {
            color: #fff;
        }
    }
</style>