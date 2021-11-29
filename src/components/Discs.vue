<template>
    <div>
        <SelectNotDinamic @genre="FilterGenre"/>
        <ul class="mt-2">
            <li class="mt-2" v-for="(element, i) in filteredDiscographi" :key="`key-${i}`">
                <img :src="element.poster" alt="">
                <h1> {{ element.title }} </h1>
                <h2> {{ element.author }} </h2>
                <h2> {{ element.year }} </h2>
                <h3> {{ element.genre }} </h3>
            </li>
        </ul>

    </div>
</template>

<script>

import Axios from 'axios';
import SelectNotDinamic from '@/components/SelectNotDinamic';


export default {
    name: 'Discs',

    data() {
        return {
        discogrphi: [],
        actualGenre: "",
        }
    },

    
    components: {
        SelectNotDinamic,
    },

    created() {
        this.call_api()
    },

    computed: {
        filteredDiscographi() {
            if (this.actualGenre === "") {
                return this.discogrphi.response
            } else {
                return this.discogrphi.response.filter((item) => {
                    return item.genre === this.actualGenre
                })
            }
        }
    },

    methods: {
        call_api() {
            Axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then(result => this.discogrphi = result.data)
            .catch(error => console.log(error));
        },

        FilterGenre(genre) {
            this.actualGenre = genre
        },
    },
    
}
</script>

<style scoped lang="scss">
    ul {
        list-style: none;
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        li {
            display: flex;
            flex-direction: column;
            background-color: #2e3a46;
            margin: 10px;
            width: calc((100% / 8) - 20px);
            padding: 15px;
            img {
                width: 100%;
            }
            h1 {
                font-size: 15px;
                text-transform: uppercase;
                text-align: center;
                color: white;
                margin-top: 25px;
            }
            h2 {
                font-size: 13px;
                text-align: center;
                color: #7f7f7f;
                margin-top: 10px;
            }
            h3 {
                font-size: 13px;
                text-align: center;
                color: white;
                margin-top: 10px;
            }
        }
    }
</style>