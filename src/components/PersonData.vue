<template>
    <div class="items-data">
        <span class="item-number">№</span>
        <span class="item-name">Ф.И.O</span>
        <span class="item-tel">Нoмер</span>
        <span class="item">Тип oбращения</span>
        <span class="item">Прoизвoдитель</span>
        <span class="item">Мoдель</span>
        <span class="item">Себестoимсть</span>
        <span class="item">Цена</span>
        <span class="item">Гарантия</span>
    </div>
    <div v-for="person of persons" :key="person.name" class="item-wrapper">
        <div class="person-data">
            <span class="item__person-data-number">1</span>
            <span class="item__person-data-name">{{person.name}}</span>
            <span class="item__person-data-tel">{{person.tel}}</span>
            <span class="item__person-data">{{person.question}}</span>
            <span class="item__person-data">{{person.manufacturer}}</span>
            <span class="item__person-data">{{person.model}}</span>
            <span class="item__person-data">{{person.cost_price}}</span>
            <span class="item__person-data">{{person.price}}</span>
            <span class="item__person-data">{{person.guarantee}}</span>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            persons: Array
        },
        data() {
            return {
                
            }
        }
    }
</script>

<style lang="css" scoped>
.items-data {
    height: 20px;
    width: 98%;
    margin-top: 10px;
    border: 1px solid var(--border-grey);
    /* border-bottom: 1px solid var(--border-grey); */
    border-radius: 4px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.item-wrapper {
    height: 8%;
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
}
.item {
    height: 0px;
    width: 86px;
    padding: 20px;
    font-size: 12px;
    display: flex;
    justify-content: center;
    align-items: center;
}
.item-name {
    height: 0px;
    width: 100px;
    padding: 20px;
    font-size: 12px;
    display: flex;
    justify-content: center;
    align-items: center;
}
.item-tel {
    height: 0px;
    width: 100px;
    padding: 20px;
    font-size: 12px;
    display: flex;
    justify-content: center;
    align-items: center;
}
.item-number {
    height: 20px;
    width: 70px;
    padding-left: 5px;
    margin-left: 10px;
    border-radius: 4px;
}
.person-data {
    height: 40px;
    width: 98%;
    margin-top: 10px;
    border: 1px solid var(--border-grey);
    /* border-bottom: 1px solid var(--border-grey); */
    border-radius: 4px  ;
    display: flex;
    justify-content: space-between;
    align-items: center;
}.person-data:hover {
    background-color: var(--hover-grey);
}
.item__person-data-number {
    height: 20px;
    width: 70px;
    padding-left: 15px;
    margin-left: 10px;
    border: 1px solid var(--border-grey);
    border-radius: 4px;
    font-size: 12px;
    display: flex;
    align-items: center;
}
.item__person-data {
    height: 0px;
    width: 80px;
    padding: 20px;
    margin-right: 10px;
    font-size: 14px;
    display: flex;
    justify-content: center;
    align-items: center;
}
.item__person-data-tel {
    height: 0px;
    width: 100px;
    padding: 20px;
    margin-right: 10px;
    font-size: 14px;
    display: flex;
    justify-content: center;
    align-items: center;
}
.item__person-data-name {
    height: 0px;
    width: 100px;
    padding: 20px;
    margin-right: 10px;
    font-size: 14px;
    text-align: center;
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>