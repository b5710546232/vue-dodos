<template>
    <div class="wrapper">
        <div v-for="item in todos">
            <div class="container">
                <div class="card">
                    </header>
                    <div class="card-content">
                        <div class="content">
                            {{item.title}}
                            <small>11:09 PM - 1 Jan 2016</small>
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
        width: 100%;
    }

    
    .card {
        width: 100%;
        margin: 1%;
    }
</style>