<template>
    <section>
        <div class="album-card">
            <div class="d-flex flex-column align-items-center">
                <img src="../assets/logo.png" alt="Lorem">
                <h3>Lorem</h3>
                <h5>Ipsum</h5>
                <span>asd</span>
                <span>asd</span>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'AlbumSection',

}
</script>

<style scoped lang="scss">
    .album-card {
        width: calc(100% / 8);
        padding: 5px;
        margin: 5px 8px;
        background: #2e3a46;

        img {
            width: 100%;
        }
    }

</style>