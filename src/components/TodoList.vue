<template>
    <div class="wrapper">
        <div v-for="item in list">
           <div class="container">
                <div class="card">
                </header>
                <div class="card-content">
                    <div class="content">
                        {{item}} 
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
    .wrapper {
        margin: 5%
    }
    .card{
        margin:1%
    }
</style>