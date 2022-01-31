<template>
    
        <div class=" text-center">
        
                <div class="disk-card pt-3 my-3">
                    <img :src="disk.poster" alt="">
                    <h6 class="pt-2">{{disk.title}}</h6>
                    <span>{{disk.author}}</span>
                    <p>{{disk.year}}</p>
                </div>
        
        </div>
</template>

<script>
    export default {
        props: {
            disk: Object
        }
    }
</script>

<style lang="scss" scoped>
    @import '@/style/diskCard.scss';
</style>