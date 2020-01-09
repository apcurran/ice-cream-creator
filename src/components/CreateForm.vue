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
        <div class="form-group">
            <input type="checkbox" name="flavor" id="flavor--chocolate" class="flavor">
            <label for="flavor"></label>
        </div>
    </form>
</template>

<script>
export default {
    name: "CreateForm",
    data() {
        return {
            pickedContainer: "",
        }
    }
}
</script>

<style>

</style>