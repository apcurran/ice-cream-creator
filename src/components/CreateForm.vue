<template>
    <form class="form">
        <p>Create your favorite</p>
        <div class="form-group">
            <fieldset class="cone-option">
                <legend class="cone-option__legend">Container</legend>
                <div class="form-group--inner">
                    <input v-model="pickedContainer" type="radio" value="Bowl" name="container" id="container--bowl" class="cone-option__input">
                    <label for="container--bowl" class="cone-option__label">Bowl</label>
                </div>
                <div class="form-group--inner">
                    <input v-model="pickedContainer" type="radio" value="Cone" name="container" id="container--cone" class="cone-option__input">
                    <label for="container--cone" class="cone-option__label">Cone</label>
                </div>
            </fieldset>
        </div>
        <section class="flavor">
            <h2 class="flavor__title">Flavors:</h2>
            <div class="form-group">
                <input v-model="flavors" value="Chocolate" type="checkbox" name="flavor" id="flavor--chocolate" class="flavor__input">
                <label class="flavor__label" for="flavor--chocolate">Chocolate</label>
            </div>
            <div class="form-group">
                <input v-model="flavors" value="Vanilla" type="checkbox" name="flavor" id="flavor--vanilla" class="flavor__input">
                <label class="flavor__label" for="flavor--vanilla">Vanilla</label>
            </div>
            <div class="form-group">
                <input v-model="flavors" value="Strawberry" type="checkbox" name="flavor" id="flavor--strawberry" class="flavor__input">
                <label class="flavor__label" for="flavor--strawberry">Strawberry</label>
            </div>
        </section>
        <section class="topping">
            <h2 class="topping__title">Toppings:</h2>
            <div class="form-group">
                <input v-model="toppings" value="Peanuts" type="checkbox" name="topping" id="topping--peanuts" class="topping__input">
                <label class="topping__label" for="topping--peanuts">Peanuts</label>
            </div>
            <div class="form-group">
                <input v-model="toppings" value="Oreos" type="checkbox" name="topping" id="topping--oreos" class="topping__input">
                <label class="topping__label" for="topping--oreos">Oreos</label>
            </div>
            <div class="form-group">
                <input v-model="toppings" value="Caramel" type="checkbox" name="topping" id="topping--caramel" class="topping__input">
                <label class="topping__label" for="topping--caramel">Caramel</label>
            </div>
        </section>
    </form>
</template>

<script>
export default {
    name: "CreateForm",
    data() {
        return {
            pickedContainer: "",
            flavors: [],
            toppings: []
        }
    },
    methods: {
        addFlavor(flav) {
            this.flavors.push(flav);
        }
    }
}
</script>

<style>

</style>