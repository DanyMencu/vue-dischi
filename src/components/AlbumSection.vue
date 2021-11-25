<template>
    <section class="container d-flex justify-content-center">
        <div class="d-flex flex-wrap justify-content-center"
        v-if="albumCollection != null">

            <div class="album d-flex"
            v-for="(element, index) in albumCollection" :key="`Album-${index}`">
                <AlbumCard 
                    :Image="element.poster"
                    :MainTitle="element.title"
                    :Author="element.author"
                    :Text1="element.year"
                    :Text2="element.genre"
                />
            </div>

        </div>

            <DiscLoader v-else />
    </section>
</template>

<script>
import axios from 'axios';
import AlbumCard from '@/components/AlbumCard.vue';
import DiscLoader from '@/components/DiscLoader.vue';

export default {
    name: 'AlbumSection',
    components: {
        AlbumCard,
        DiscLoader,
    },
    data() {
        return {
            albumCollection: null,
        };
    },
    created() {
        this.getAlbum();
    },
    methods: {
        getAlbum() {
            /* Call API for data */
            axios
                .get('https://flynn.boolean.careers/exercises/api/array/music')
                .then(result => {
                    this.albumCollection = result.data.response;
                })
                .catch(error => console.log(error));
        }
    }

}
</script>

<style scoped lang="scss">

    section {
        text-align: center;
        padding: 3.5rem 1.5rem;
        color: #fff;
    }

    .album {
        width: calc(100% / 8);
        padding: 7px;
    }

</style>