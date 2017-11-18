<template>
    <div id = "app" class="app">
        <!--keep alive is to ensure that the components do not reset-->
        <keep-alive>
            <!--:is is binding the property of visible component to the component tag-->
            <component :is = "visible_component"></component>
        </keep-alive>
        <div class = "large-12 medium-12 columns">
            <div class = "button medium default send" @click = "send()">Send</div>
            <div class = "button medium default back" @click = "visible_component='message'">Back</div>
        </div>
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
        },
        methods:{
            send(){
                this.visible_component = 'sent';
                alert("Message will be sent to admin")
                console.log(this.$options.name)
            }
        }
    }
</script>

<style lang = "scss">
    .app{
        padding: 40px 0 40px;
        .back{
            margin-left: 50px;
        }
        .send{
            margin-left: 210px;
        }
    }
</style>
