<template>
    <div class="modal-add">
        <div class="modal-add-client">

        </div>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="css" scoped>
.modal-add {
    height: calc(100vh - 1px);
    width: 100%;
    margin-top: -60px;
    background-color: var(--opasity-grey);
    position: absolute;
    z-index: 100;
    display: flex;
    justify-content: center;
    align-items: center;
}
.modal-add-client {
    height: 90%;
    width: 50%;
    background-color: #fff;
    border-radius: 4px;
}
</style>