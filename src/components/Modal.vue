<script setup>
    import cerrarModal from '../assets/img/cerrar.svg'
    const emit = defineEmits(['cerrar-modal']);
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

        <div class="contenedor">
            <form>
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

</style>