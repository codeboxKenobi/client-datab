<template>
    <div class="modal-add">
        <div class="modal-add-client">
            <div class="numb-close">
                <div class="person-number">
                    <span></span>
                </div>
                <div class="close-modal">
                    <img @click="closeModalAdd" src="../assets/close.png" alt="">
                </div>
            </div>
            <div class="add-form">
                <form class="form-person" method="post">
                    <input v-model="name" class="form-input" placeholder="Ф.И.O" type="text">
                    <input v-model="tel" class="form-input" placeholder="Нoмер" type="text">
                    <input v-model="question" class="form-input" placeholder="Тип oбращения" type="text">
                    <input v-model="manufacturer" class="form-input" placeholder="Прoизвoдитель" type="text">
                    <input v-model="model" class="form-input" placeholder="Мoдель" type="text">
                    <input v-model="cost_price" class="form-input" placeholder="Себестoимсть" type="text">
                    <input v-model="price" class="form-input" placeholder="Цена" type="text">
                    <input v-model="guarantee" class="form-input" placeholder="Гарантия" type="text">
                    <button @click="sendData" class="form-submit" type="button">Submit</button>
                </form>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    data() {
        return {
            name: "",
            tel: "",
            question: "",
            manufacturer: "",
            model: "",
            cost_price: "",
            price: "",
            guarantee: ""
        }
    },

    methods: {
            reloadPage() {
                window.location.reload();
            },
        closeModalAdd() {
            this.$parent.closeModalAdd()
        },
        CreatePerson(name, tel, question, manufacturer, model, cost_price, price, guarantee) {
            this.name = name
            this.tel = tel
            this.question = question
            this.manufacturer = manufacturer
            this.model = model
            this.cost_price = cost_price
            this.price = price
            this.guarantee = guarantee
        },
        async sendData() {
            let person = new this.CreatePerson(
                this.name, 
                this.tel, 
                this.question, 
                this.manufacturer, 
                this.model, 
                this.cost_price, 
                this.price, 
                this.guarantee
            )
            let response = await fetch('http://localhost:5000/api/person', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json;charset=utf-8'
                },
                body: JSON.stringify(person)
            });
            console.log(response);
            this.closeModalAdd()
            // this.reloadPage()
        },
    },
    mounted() {
    
    }
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
    border: 1px solid var(--border-grey);
    border-radius: 4px;
    border-radius: 4px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
}
.numb-close {
    height: 5%;
    width: 96%;
    margin-top: 10px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.person-number {
    height: 90%;
    width: 15%;
    /* border: 1px solid var(--border-grey); */
    border-radius: 4px;
    padding-left: 10px;
    display: flex;
    align-items: center;
}
.close-modal {
    height: 90%;
    width: 15%;
    padding-left: 10px;
    display: flex;
    justify-content: flex-end;
    align-items: center;
}
.add-form {
    height: 80%;
    width: 80%;
    background-color: #fff;
    margin-bottom: 40px;
    display: flex;
    justify-content: center;
    align-items: center;
}
.form-person {
    height: 100%;
    width: 100%;
    margin-bottom: 40px;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;
}
.form-input {
    height: 6%;
    width: 90%;
    border: 1px solid var(--border-grey);
    border-radius: 4px;
    outline: none;
    margin-top: 10px;
    padding-left: 10px;
    padding-right: 10px;
    color: var(--border-grey);
    display: flex;
    justify-content: space-evenly;
    align-items: center;
}
.form-submit {
    height: 6%;
    width: 30%;
        margin-top: 50px;
    border: none;
    background-color: #fff;
    border-left: 1px solid var(--border-grey);
    border-right: 1px solid var(--border-grey);
    border-radius: 4px;
    outline: none;
    display: flex;
    justify-content: space-evenly;
    align-items: center;
}
.form-submit:hover {
    background-color: var(--hover-grey);
}
</style>