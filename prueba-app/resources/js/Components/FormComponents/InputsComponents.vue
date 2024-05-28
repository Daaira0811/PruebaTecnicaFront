<style scoped>
@import "../../../css/styles.css";
</style>
<template id="formInputs" width="100%">
    <div class="d-flex input-container">
        <i class="bi bi-list-stars icon"></i>

        <div class="input-group">
            <input
                type="text"
                class="input-field input-button"
                id="hobbiesInput"
                aria-describedby="button-addon2"
               
            />
            <button
                @click="$emit('decreaseBy', 1)"
                class="btn button-end-rounded"
                type="button"
                id="button-addon2"
            >
                <i class="bi bi-x-lg"></i>
            </button>
        </div>
    </div>
</template>
