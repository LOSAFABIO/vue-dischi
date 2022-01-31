<template>
<div class="container">
    <div class="row g-3 row-cols-5 container-dischi">
        <div 
        v-for="(DiscoSingolo,indice) in dischiArray" 
        :key="indice"
        class="col-2 m-3 p-2 ">
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

<style lang="scss" scoped>

@import "../../assets/style/Vars.scss";

.row{
    width: 80%;
    margin: 80px auto;
    .col-2{
        background-color: $mainColor;
}
}

</style>
