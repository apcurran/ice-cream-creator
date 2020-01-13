<template>
    <form @submit.prevent="sendIceCream" class="form">
        <fieldset class="container cone-option" required>
            <legend class="cone-option__legend">Container Type</legend>
            <h2 class="container__title cone-option__title">Container Type:</h2>
            <div class="form-group-wrapper">
                <div class="form-group">
                    <label for="container--bowl" class="form-group__label">Bowl</label>
                    <input v-model="order.pickedContainer" type="radio" value="Bowl" name="container" id="container--bowl" class="cone-option__input">
                </div>
                <div class="form-group">
                    <label for="container--cone" class="form-group__label">Cone</label>
                    <input v-model="order.pickedContainer" type="radio" value="Cone" name="container" id="container--cone" class="cone-option__input">
                </div>
            </div>
        </fieldset>
        <section class="container flavor">
            <h2 class="container__title flavor__title">Flavors:</h2>
            <div class="form-group-wrapper">
                <div class="form-group">
                    <label class="form-group__label" for="flavor--chocolate">Chocolate</label>
                    <input v-model="order.flavors" value="Chocolate" type="checkbox" name="flavor" id="flavor--chocolate" class="flavor__input">
                </div>
                <div class="form-group">
                    <label class="form-group__label" for="flavor--vanilla">Vanilla</label>
                    <input v-model="order.flavors" value="Vanilla" type="checkbox" name="flavor" id="flavor--vanilla" class="flavor__input">
                </div>
                <div class="form-group">
                    <label class="form-group__label" for="flavor--strawberry">Strawberry</label>
                    <input v-model="order.flavors" value="Strawberry" type="checkbox" name="flavor" id="flavor--strawberry" class="flavor__input">
                </div>
            </div>
        </section>
        <section class="container topping">
            <h2 class="container__title topping__title">Toppings:</h2>
            <div class="form-group-wrapper">
                <div class="form-group">
                    <label class="form-group__label" for="topping--peanuts">Peanuts</label>
                    <input v-model="order.toppings" value="Peanuts" type="checkbox" name="topping" id="topping--peanuts" class="topping__input">
                </div>
                <div class="form-group">
                    <label class="form-group__label" for="topping--oreos">Oreos</label>
                    <input v-model="order.toppings" value="Oreos" type="checkbox" name="topping" id="topping--oreos" class="topping__input">
                </div>
                <div class="form-group">
                    <label class="form-group__label" for="topping--caramel">Caramel</label>
                    <input v-model="order.toppings" value="Caramel" type="checkbox" name="topping" id="topping--caramel" class="topping__input">
                </div>
            </div>
        </section>
        <section class="container">
            <input class="form__submit" type="submit" value="Order">
        </section>
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

.form {
    width: 35rem;
    max-width: 92.5%;
    margin: 2.5rem auto 0 auto;
    background-color: #fff;
    border-radius: 4px;
}

.form-group-wrapper {
    display: flex;
}

.form-group {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.form-group:not(:last-child) {
    margin-right: 2rem;
    margin-bottom: 1.5rem;
}

.form-group__label {
    margin-bottom: .5rem;
}

.cone-option {
    /* Remove default border */
    border: none;
}

.container {
    padding: 2rem;
}

.container__title {
    margin-bottom: .65rem;
}

.cone-option,
.flavor,
.topping {
    border-bottom: 1px solid #dfdfdf;
}

/* Keep for accessiblity, but position off-screen */
.cone-option__legend {
    position: absolute;
    left: -150%;
}

.cone-option__title,
.flavor__title,
.topping__title {
    font-size: 1.5rem;
    font-weight: 400;
}

.form__submit {
    padding: .75rem 2rem;
    color: #fff;
    background-color: #2b32b2;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    text-transform: uppercase;
    font-weight: 600;
    letter-spacing: .06em;
}

.form__submit:hover {
    background-color: hsl(237, 61%, 53%);
}

</style>