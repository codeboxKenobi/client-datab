<template>
    <div class="content">
        <div class="nav-sidebar">
            <div class="nav-button">
                <button @click="openModalAdd" class="n-button">+</button>
                <button @click="openModalWarehouse" class="n-button">Склад</button>
                <button @click="openModalAnalytics" class="n-button">Аналитика</button>
            </div>
        </div>
        <ClientsWrapper />
        <ModalAdd v-if="isOpenAdd" />
        <ModalWarehouse v-if="isOpenWarehouse" />
        <ModalAnalytics v-if="isOpenAnalytics"  />

        
    </div>
</template>

<script>
import ClientsWrapper from './ClientsWrapper.vue'
import ModalAdd from './ModalAdd.vue'
import ModalWarehouse from './ModalWarehouse.vue'
import ModalAnalytics from './ModalAnalytics.vue'


    export default {
        data() {
            return {
                isOpenAdd: false,
                isOpenWarehouse: false,
                isOpenAnalytics: false
            }
        },
        methods: {
            openModalAdd() {
                this.isOpenAdd = true
            },
            openModalWarehouse() {
                this.isOpenWarehouse = true
            },
             openModalAnalytics() {
                this.isOpenAnalytics = true
            },
            closeModalAdd() {
                this.isOpenAdd = false
            }
        },
        components: {
            ClientsWrapper,
            ModalAdd,
            ModalWarehouse,
            ModalAnalytics
        }
    }
</script>


<style lang="css" scoped>
.content {
    height: calc(100vh - 60px);
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center
}
.nav-sidebar {
    height: calc(96vh - 66px);
    width: 22%;
    max-width: 120px;
    background-color: var(--color-grey);
    border: 1px solid var(--border-grey);
    /* border-right: 1px solid var(--border-grey); */
    border-radius: 4px;
    color: var(--border-grey);
    padding-left: 10px;
    padding-right: 10px;
    margin-left: 20px;
    margin-right: 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
}
.nav-button {
    height: 220px;
    width: 90%;
    max-width: 120px;
    background-color: var(--color-grey);
    /* border-top: 1px solid var(--border-grey);
    border-bottom: 1px solid var(--border-grey); */
    color: var(--border-grey);
    padding-left: 10px;
    padding-right: 10px;
    margin-top: 6px;
    margin-left: 20px;
    margin-right: 20px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
.n-button {
    height: 30px;
    width: 90%;
    margin: 10px;
    color: var(--border-grey);
    border: none;
    border-top: 1px solid var(--border-grey);
    border-bottom: 1px solid var(--border-grey);
    border-radius: 4px;
    background-color: var(--color-grey);
}
.n-button:hover {
    background-color: var(--hover-grey);
}
</style>
