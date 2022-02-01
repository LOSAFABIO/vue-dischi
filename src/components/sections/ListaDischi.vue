<template>
<div class="container">
    <div v-if="!loading">
        <div class="row w_30">
            <div class="col">
                <Genere 
                @filtra ="filtraAlbum" />
            </div>
        </div>
        <div class="row g-3 row-cols-8 container-dischi ">
            <div 
            v-for="(DiscoSingolo,indice) in albumSelect" 
            :key="indice"
            class="col-2 m-3 p-2 ">
            <DiscoSingolo
            :disco="DiscoSingolo" />
            </div>
        </div>
    </div>
    <Loader v-else /> 
</div>

</template>

<script>

import axios from "axios";
import DiscoSingolo from "../commons/DiscoSingolo.vue";
import Genere from "../commons/Genere.vue";
import Loader from "../commons/Loader.vue";


export default {
    name       : "ListaDischi",
    components : {
        DiscoSingolo,
        Genere,
        Loader
    },
    data() {
        return{
            apiURL      : "https://flynn.boolean.careers/exercises/api/array/music",
            dischiArray : [],
            loading     : true,
            filtroAlbum : ""
        }
    },

    created() {
        this.getDischi();
    },
    computed: {
        albumSelect(){
            if(this.filtroAlbum == "All"){
                return this.dischiArray
            }
            return this.dischiArray.filter( (album) => {
                return album.genre.toLowerCase().includes(this.filtroAlbum.toLowerCase());
            });
        }
    },
    methods:{
        getDischi(){
            axios.get(this.apiURL)
            .then((risposta) => {
                // handle success
                this.dischiArray = risposta.data.response;
                this.loading = false
            })
            .catch(function (error) {
                // handle error
                console.log(error);
            })

        },
        filtraAlbum(inputCerca){
            this.filtroAlbum = inputCerca;
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

.w_30{
    width: 30%;
}

</style>
