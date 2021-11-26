<template>
    <section>
        <div class="container h-100">
            <div class="row justify-content-between align-items-center h-100">
                <div class="col-2 h-100">
                    <img src="@/assets/logo.png" alt="Spotify logo">
                </div>
                <div class="col-4 d-flex">
                    <label for="genre">Musical genre:</label>
                    <select name="genre" v-model="Genres" @change="$emit('genreSelect', Genres)">
                        <option value="">All</option>
                        <option v-for="(element, index) in allGenres" :key="`Genre-${index}`" :value="element"> {{ element }} </option>

                    </select>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'Header',
    props: {
        allGenres: Array,
    },
    data() {
        return {
            Genres: '',
        }
    }
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

    label {
        color: #fff;
        padding-right: 10px;
    }

    select {
        width: 50%;
    }
}

</style>