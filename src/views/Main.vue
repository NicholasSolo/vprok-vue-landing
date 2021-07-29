<template>
    <div class="wrapper">
        <Header/>
    </div>
</template>

<script>
import Header from '@/components/Header.vue'
    export default {
        name: 'Main',
        components: {
            Header
        },
        data() {
            return {

            }
        }
    }
</script>

<style lang="scss" scoped>
    .wrapper {
        max-width: 1440px;
        // background: red;
    }
</style>