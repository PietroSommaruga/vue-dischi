<template>
    <main>
        <div class="container">
            <div class="card-container">
                <disk-card v-for="(disk, index) in discs" :key="index" :disk="disk"/>
            </div>
        </div>

    </main>
</template>

<script>
    import DiskCard from './DiskCard.vue'
    export default {
        components: {
            DiskCard,
        },
        props: {
            discs: Array
        }
    }
</script>

<style lang="scss" scoped>
    @import '@/style/mainContainer.scss';
</style>