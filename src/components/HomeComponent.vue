<template>
    <template v-if="showMainComponent">
        <ButtonsComponent @click="selectedItem"></ButtonsComponent> 
        <!-- buttons recoge el evento e indica la función que se tiene que ejecutar 
            (dentro del mismo <Home>) que estará en methods -->
        <EscenaComponent id="history" :history="history" :currentSentence="currentSentence"/>
    </template>
    <template v-else>
        <button @click="showMainComponent = true">Començar</button>
    </template>
</template>

<script>
import EscenaComponent from './/EscenaComponent.vue'
import ButtonsComponent from './/ButtonsComponent.vue'

export default {
    name: 'HomeComponent',
    components: {
        EscenaComponent,
        ButtonsComponent
    }, 
    data(){
        return {
            history: [
                {text: "El nostre heroi estava surant per l'espai sideral quan a la llunyania va albirar una nau espacial", number: 0},
                {text: "Sentia curiositat per l'interior de la nau i es va posar a inspeccionar-la. Va arribar a una sala amb dues portes.", number: 1},
                {text: "L'heroi va decidir travessar la porta que el portava a casa.", number: 2},
                {text: "Mentrestant, altres herois no van tenir tanta sort en la seva elecció...", number: 3},
                ],
            currentSentence: 0,
            showMainComponent: false
        }
    }, 
    methods:{
        selectedItem(param){
            //incrementa o decrementa según sea el botón pulsado de <botones>, 
            //ya que cada uno tendrá una referencia diferente
            if (this.currentSentence > 0 && param < 0) {
                this.currentSentence += param;
            } 
            if (this.currentSentence < this.history.length -1 && param > 0) {
                this.currentSentence += param;
            }
        }
    }
}

</script>