<template>
    <div id="app">
        <img alt="Vue logo" src="./assets/logo.png">
        <HelloWorld :msg="message"/>
    </div>
</template>

<script lang="ts">
    import {Component, Vue} from 'vue-property-decorator';
    import HelloWorld from './components/HelloWorld.vue';
    import axios from 'axios';

    @Component({
        components: {
            HelloWorld,
        },
    })
    export default class App extends Vue {
        protected message: string = 'Welcome to Your Vue.js App';

        public async created() {
            const response = await axios.get('http://api.omicron.net/ping');

            this.message = response.data.data;
        }
    }
</script>

<style lang="scss">
    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>
