<template>
    <form @submit.prevent="sendIceCream" class="form">
        <p>Create your favorite</p>
        <div class="form-group">
            <fieldset class="cone-option">
                <legend class="cone-option__legend">Container</legend>
                <div class="form-group--inner">
                    <input v-model="order.pickedContainer" type="radio" value="Bowl" name="container" id="container--bowl" class="cone-option__input">
                    <label for="container--bowl" class="cone-option__label">Bowl</label>
                </div>
                <div class="form-group--inner">
                    <input v-model="order.pickedContainer" type="radio" value="Cone" name="container" id="container--cone" class="cone-option__input">
                    <label for="container--cone" class="cone-option__label">Cone</label>
                </div>
            </fieldset>
        </div>
        <section class="flavor">
            <h2 class="flavor__title">Flavors:</h2>
            <div class="form-group">
                <input v-model="order.flavors" value="Chocolate" type="checkbox" name="flavor" id="flavor--chocolate" class="flavor__input">
                <label class="flavor__label" for="flavor--chocolate">Chocolate</label>
            </div>
            <div class="form-group">
                <input v-model="order.flavors" value="Vanilla" type="checkbox" name="flavor" id="flavor--vanilla" class="flavor__input">
                <label class="flavor__label" for="flavor--vanilla">Vanilla</label>
            </div>
            <div class="form-group">
                <input v-model="order.flavors" value="Strawberry" type="checkbox" name="flavor" id="flavor--strawberry" class="flavor__input">
                <label class="flavor__label" for="flavor--strawberry">Strawberry</label>
            </div>
        </section>
        <section class="topping">
            <h2 class="topping__title">Toppings:</h2>
            <div class="form-group">
                <input v-model="order.toppings" value="Peanuts" type="checkbox" name="topping" id="topping--peanuts" class="topping__input">
                <label class="topping__label" for="topping--peanuts">Peanuts</label>
            </div>
            <div class="form-group">
                <input v-model="order.toppings" value="Oreos" type="checkbox" name="topping" id="topping--oreos" class="topping__input">
                <label class="topping__label" for="topping--oreos">Oreos</label>
            </div>
            <div class="form-group">
                <input v-model="order.toppings" value="Caramel" type="checkbox" name="topping" id="topping--caramel" class="topping__input">
                <label class="topping__label" for="topping--caramel">Caramel</label>
            </div>
        </section>
        <input type="submit" value="Order">
    </form>
</template>

<script>
export default {
    name: "CreateForm",
    data() {
        return {
            order: {
                pickedContainer: "",
                flavors: [],
                toppings: []
            }
        }
    },
    methods: {
        sendIceCream() {
            this.$emit("sendIceCream", {
                container: this.order.pickedContainer,
                flavors: this.order.flavors,
                toppings: this.order.toppings
            });

            // Clear after emitting
            this.clearInputs();
        },
        clearInputs() {
            this.order.pickedContainer = "";
            this.order.flavors = [];
            this.order.toppings = [];
        }
    }
}
</script>

<style>

</style>