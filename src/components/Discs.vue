<template>
    <h1>CIAO</h1>
</template>

<script>

import Axios from 'axios';

export default {
    name: 'Discs',

    data() {
        return {
        var: []
        }
    },

    methods: {
        call_api() {
            Axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then(result => this.var = result.data)
            .catch(error => console.log(error));
        }
    },
    
    created() {
        this.call_api()
    },
}
</script>

<style leng="scss" scoped>

</style>