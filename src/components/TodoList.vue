<template>
    <div class="wrapper">
        <div v-for="item in todos">
            <div class="container">
                <div class="card is-desktop is-mobile is-fullwidth">
                    </header>
                    <div class="card-content">
                        <div class="content">
                            {{item.title}}
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    props:['todos'],
    data () {
        return {
            list:[1,2,3,4]
        }
    },
    computed: {},
    mounted () {},
    methods: {},
    components: {}
}
</script>
<style scoped>
    .container {
        overflow: hidden;
    }
    
    .card {
        /*width: 100%;*/
        margin-bottom: 1%;
    }
</style>