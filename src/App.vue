<template>
    <div id = "app">
        <!--keep alive is to ensure that the components do not reset-->
        <keep-alive>
            <!--:is is binding the property of visible component to the component tag-->
            <component :is="visible_component"></component>
        </keep-alive>
        <div class="button medium default" @click="visible_component='sent'">Send</div>
        <div class="button medium default" @click="visible_component='message'">Back</div>
    </div>
</template>

<script>
    import Message from './components/Message.vue'
    import Sent from './components/Sent.vue'
    export default {
        name: 'app',
        data() {
            return {
                visible_component: 'message'
            }
        },
        components: {
            'message': Message,
            'sent': Sent
        }
    }
</script>

<style lang = "scss">
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }

    h1, h2 {
        font-weight: normal;
    }

    ul {
        list-style-type: none;
        padding: 0;
    }

    li {
        display: inline-block;
        margin: 0 10px;
    }

    a {
        color: #42b983;
    }
</style>
