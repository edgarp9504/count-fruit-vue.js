<template>
    <div>
        <ul class="list-group" >
            <li v-for="(item, index) of orderArray" :key="item.id" @click="aumentar(index)"
            class="list-group-item d-flex justify-content-between align-items-center">
                {{index +1}} - {{item.nombre}}
                <span class="badge badge-primary badge-pill">{{item.cantidad}}</span>
            </li>
        </ul>
        <button class="btn btn-danger btn-block" @click="reiniciar"> Reiniciar</button>
    </div>
</template>

<script>
import {mapState, mapMutations} from 'vuex';

export default {
    name: 'Lista',
    computed:{
        ...mapState(['frutas']),
        orderArray(){   
            return this.frutas.slice().sort( (a, b) => b.cantidad - a.cantidad )
        }
    },
    watch:{

        
    },
    methods:{
        ...mapMutations(['aumentar']),
        ...mapMutations(['reiniciar']),

    }

}
</script>>