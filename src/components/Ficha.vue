<template>
    <!-- <h1>Hijo</h1> -->
    <div class="display">
        <button class="boton">
            {{ cosa.ropa }} ({{ cosa.marca }})
        </button>
        <div class="estrellas">
            <span v-for="index in cosa.nota" :key="index">
                <!-- <img src="https://www.html6.es/img/estrella.png" alt=""> -->

                <img src="@/assets/Leo.jpg" alt="">
            </span>
        </div>
        <button @click="incrementarNota(cosa.nota,index)">+</button>
    </div>
</template>


<script setup>
const emito=defineEmits(['retorno'])
const incrementarNota=(a,i)=>{
    emito('retorno',a,i)
}

const props = defineProps({
    cosa: String,
    index:Number
})
</script>

<style scoped>
.display{
    display:flex;
    align-items:center;
}
.display img{
    width: 15px;
    margin: 1px;
}
.diplay button{
    margin-right: 20px;
}
.boton{
    width: 165px;
}
.estrellas{
    width: 125;
    height: 22px;
}
</style>
