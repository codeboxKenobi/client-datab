<template>
    <div class="modal-analytics">
        <div class="analytics">

        </div>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="css" scoped>
.modal-analytics {
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
.analytics {
    height: 90%;
    width: 80%;
    background-color: #fff;
    border-radius: 4px;
}
</style>