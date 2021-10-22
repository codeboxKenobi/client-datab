<template>
    <div class="clients-wrapper">
        <PersonData :persons="allPerson" />
    </div>
</template>

<script>
import PersonData from './PersonData.vue'

    export default {
        data() {
            return {
                allPerson: [],
            }
        },
        methods: {
            async getPersons() {
                let resp = await fetch('http://localhost:5000/api/person')
                let personData = await resp.json()
                this.allPerson = personData
            }
        },
        mounted() {
            this.getPersons()
        },
        components: {
            PersonData
        }
    }
</script>

<style lang="css" scoped>
.clients-wrapper {
    height: calc(94vh - 52px);
    width: 100%;
    margin-right: 20px;
    background-color: var(--color-grey);
    border: 1px solid var(--border-grey);
    /* border-right: 1px solid var(--border-grey); */
    border-radius: 4px;
    overflow-x: hidden;
    overflow-y: scroll;
    -webkit-overflow-scrolling: touch;
    scrollbar-color: transparent transparent;
    overflow: -moz-scrollbars-none;
    display: flex;
    flex-direction: column;
    align-items: center;
}
.clients-wrapper::-webkit-scrollbar {
    display:none;
}

</style>