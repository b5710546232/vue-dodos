<template>
    <div class="wrapper">
        <div v-for="item in todos">
            <div class="container card is-desktop is-mobile is-fullwidth">
                </header>
                <div class="card-content">
                    <div class="content">

                        <div class="columns is-mobile">
                            <div class="column is-8">
                                <div v-if="isEditMode">Edditing</div>
                                <div v-else>{{item.title}}</div>
                            </div>
                            <div class="column">
                                <!--<input type="text" class="input is-fullheight is-fullheight">-->
                                <!--<div class="button is-pulled-right" @click="addTodo(todoInput),todoInput=''">Edit</div>-->
                            </div>
                            <div class="column">
                                <!--<input type="text" class="input is-fullheight is-fullheight">-->
                                <!--<div class="button is-pulled-right" @click="onCloseModal">Cancel</div>-->
                                <span v-if="isEditMode"><a href="#" class="fa fa-times fa-3x is-pulled-right"
                                    @click="onCloseModal"></a></span>
                            </div </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    props:['todos','isEditMode'],
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