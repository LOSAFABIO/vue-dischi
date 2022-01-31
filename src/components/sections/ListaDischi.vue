<template>
<div class="container">
    <div class="row row-cols-5 container-dischi">
        <div 
        v-for="DiscoSingolo in dischiArray" 
        :key="DiscoSingolo"
        class="col">
        <DiscoSingolo
        :disco="DiscoSingolo" />
        </div>
    </div>
</div>

</template>

<script>

import axios from "axios";
import DiscoSingolo from "../commons/DiscoSingolo.vue";

export default {
    name       : "ListaDischi",
    components : {
        DiscoSingolo
    },
    data() {
        return{
            apiURL  : "https://flynn.boolean.careers/exercises/api/array/music",
        dischiArray : [],
        }
    },

    created() {
        this.getDischi();
    },
    
    methods:{
        getDischi(){
            axios.get(this.apiURL)
            .then((risposta) => {
                // handle success
                this.dischiArray = risposta.data.response;
            })
            .catch(function (error) {
                // handle error
                console.log(error);
            })

        }
    }


}





</script>

<style>

</style>
