<template>
    <div class="header">
        <Logo />
        <div class="search__header">
            <img class="magnifier" src="../assets/magnifier.png" alt="">
            <input class="search-input" type="text">
        </div>
    </div>
</template>

<script>
import Logo from './Logo.vue'

    export default {
        components: { Logo },
    }
</script>


<style lang="css" scoped>
.header {
    height: 60px;
    width: 100%;
    background-color: var(--color-grey);
    border-top  : 1px solid var(--border-grey);
    border-bottom: 1px solid var(--border-grey);
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.search__header {
    height: 40px;
    width: 80%;
    margin-right: 64px;
    display: flex;
    align-items: center;
}
.search-input {
    height: 28px;
    width: 100%;
    padding-left: 30px;
    padding-right: 16px;
    color: var(--border-grey);
    background-color: var(--color-grey);
    border: 1px solid var(--border-grey);
    border-radius: 4px;
    outline: none;
    display: flex;
    align-items: center;
}
.magnifier {
    position: absolute;
    height: 16px;
    margin-left: 10px;
}
</style>