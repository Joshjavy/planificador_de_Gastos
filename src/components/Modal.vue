<script setup>
    import cerrarModal from '../assets/img/cerrar.svg'
    const emit = defineEmits(['cerrar-modal']);
    const props = defineProps({
        modal:{
            type:Object,
            required:true,
        }
    })
</script>

<template>
    <div class="modal">
        <div class="cerrar-modal">
            <img
                :src="cerrarModal"
                alt=""
                @click="$event => $emit('cerrar-modal')"
            />
        </div>

        <div class="contenedor contenedor-formulario" 
            :class="[modal.animar ? 'animar':'cerrar']"
        >
            <form

                class="nuevo-gasto"
            >
                <legend>Añadir Gasto</legend>

                <div class="campo">
                    <label for="nombre">Nombre Gasto:</label>
                    <input type="text" id="nombre" placeholder="Nombdel del gasto" />

                </div>
                <div class="campo">
                    <label for="cantidad">cantidad :</label>
                    <input type="number" id="cantidad" placeholder="cantidad del gasto" />

                </div>
                <div class="campo">
                    <label for="categoria">categoria</label>
                    <select id="categoria">
                        <option value="">-- Seleccione --</option>
                        <option value="ahorro">Ahorro</option>
                        <option value="comida">comida</option>
                        <option value="casa">casa</option>
                        <option value="gastosvarios">gastos varios</option>
                        <option value="ocio">ocio</option>
                        <option value="salud">salud</option>
                        <option value="suscripcciones">Suscripciones</option>
                    </select>
                </div>
                <input type="submit"
                    value="Registrar Gasto"
                    class=""
                    />
            </form>

        </div>


    </div>
</template>



<style scoped>
    .modal{
        position: absolute;
        background: rgb(0 0 0 / 0.9);
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
    }
    
    .cerrar-modal{
        position: absolute;
        right: 3rem;
        top:3rem;
    }
    .cerrar-modal img{
        width: 3rem;
        cursor: pointer;
        
    }

    .contenedor-formulario{
        transition-property: all;
        transition-duration: 300ms;
        transition-timing-function: ease-in;
        opacity: 0;
    }

    .contenedor-formulario.animar{
        opacity: 1;
    }
    .contenedor-formulario.cerrar{
        opacity: 0;
    }
    .nuevo-gasto{
        margin: 10rem auto 0 auto;
        display: grid;
        gap: 2rem;
    }
    .nuevo-gasto legend{
        text-align: center;
        color: var(--blanco);
        font-size: 3rem;
        font-weight: 700;
    }
    .campo{
        display: grid;
        gap: 2rem;
    }

    .nuevo-gasto input,
    .nuevo-gasto select{
        background-color: var(gris-claro);
        border-radius: 1rem;
        padding: 1rem;
        border: none;
        font-size: 2rem;
    }
    .nuevo-gasto label{
        color: var(--blanco);
        font-size: 2.3rem;
    }
    .nuevo-gasto input[type="submit"]{
        background-color: var(--azul);
        color: var(--blanco);
        font-size: 2.3rem;
        font-weight: 700;
        cursor: pointer;
    }

</style>