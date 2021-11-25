<template>
    <section>
        <div class="container h-100">
            <div class="row h-100">
                <div class="col-2 h-100">
                    <img src="@/assets/logo.png" alt="Spotify logo">
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'Header',

}
</script>

<style scoped lang="scss">

section {
    height: 10vh;
    padding: 5px;
    background: #2e3a46;
    
    img {
        height: 100%;
    }
}

</style>