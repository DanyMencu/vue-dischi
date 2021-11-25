<template>
    <div id="app">
        <!-- HEADER -->
        <Header />

        <!-- MAIN -->
        <main>
            <AlbumSection />
        </main>
    </div>
</template>

<script>
import Header from '@/components/Header.vue';
import AlbumSection from '@/components/AlbumSection.vue';

export default {
  name: 'App',
  components: {
    Header,
    AlbumSection,
  }
}
</script>

<style lang="scss">
@import '~bootstrap/scss/bootstrap.scss';
@import '@/styles/Generals';
</style>
