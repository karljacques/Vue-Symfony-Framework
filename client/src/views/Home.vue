<template>
    <div class="home">
        <img alt="Vue logo" src="../assets/logo.png">
        <HelloWorld :msg="message"/>
    </div>
</template>

<script lang="ts">
    // @ is an alias to /src
    import HelloWorld from '@/components/HelloWorld.vue'
    import {Vue, Component} from 'vue-property-decorator';

    import axios from 'axios';

    @Component({
        components: {HelloWorld},
    })
    export default class Home extends Vue {
        protected message: string = 'Welcome to Your Vue.js App';

        public async created() {
            const response = await axios.get('http://INSERT_YOUR_URL/ping');

            this.message = response.data.data;
        }
    }
</script>
