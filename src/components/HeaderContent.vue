<template>
    <header class="d-flex align-items-center">
        <img src="@/assets/logo-spotify.png" alt="">
        <select v-model="selectedValue" @change="$emit('filtro', selectedValue)">
                <option disabled value="">Scegli un genere</option>
                <option value="All">All</option>
                <option value="Jazz">Jazz</option>
                <option value="Metal">Metal</option>
                <option value="Pop">Pop</option>
                <option value="Rock">Rock</option>
            </select>
    </header>
</template>

<script>
    export default {
        name: "Header",

    data() {
        return {
            selectedValue: '',
            selectedArtist: ''
        }
    }
   
};
</script>

<style lang="scss" scoped>
    @import '@/style/headerContent';
</style>