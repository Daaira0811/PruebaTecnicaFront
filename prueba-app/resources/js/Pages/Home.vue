<script setup>
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import FooterLayout from "@/Layouts/FooterLayout.vue";
import FormInputs from "@/Components/FormComponents/InputsComponents.vue";
import ModalText2 from "@/Components/FormComponents/ModalText2.vue";
import { Head } from "@inertiajs/vue3";
import { ref } from "vue";
const counterInterest = ref(0);
const counterHobbies = ref(0);
const modalActive = ref(false);
const toggleModal = () => {
    modalActive.value = !modalActive.value;
};
</script>

<style scoped>
@import "../../css/styles.css";
</style>
<template>
    <Head title="Home">
        <!-- Se incluyen iconos de boostrap -->
        <link
            rel="stylesheet"
            href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css"
        />
        <link
            rel="stylesheet"
            href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.5.0/font/bootstrap-icons.css"
        />
    </Head>

    <AuthenticatedLayout>
        <div v-show="modalActive">
            <ModalText2
                @close="toggleModal"
                :One=One
                :Two=Two
                :Three=Three
                :Four=Four
                :Five=Five
                :Six=Six
            ></ModalText2>
        </div>
        <div class="container mt-4">
            <h1>Generador de texto</h1>
            <p>
                Completa tus datos personales para rellenar automáticamente un
                texto de presentación.
            </p>
        </div>
        <div class="container" style="height: 67vh">
            <div class="row row-form">
                <div class="col-md-3 col-sm-4">
                    <label for="nameInput" class="form-label"
                        >Nombre <sup> <i class="bi bi-asterisk"></i></sup
                    ></label>
                    <div class="d-flex input-container">
                        <i class="bi bi-person icon"></i>
                        <input
                            type="text"
                            class="input-field"
                            id="nameInput"
                            v-model="One"
                        />
                    </div>
                </div>
                <div class="col-md-3 col-sm-4">
                    <label for="lastNameInput" class="form-label"
                        >Apellido(s) <sup> <i class="bi bi-asterisk"></i></sup
                    ></label>
                    <div class="d-flex input-container">
                        <i class="bi bi-person icon"></i>
                        <input
                            type="text"
                            class="input-field"
                            id="LastNameInput"
                            v-model="Two"
                        />
                    </div>
                </div>
                <div class="col-md-3 col-sm-4">
                    <label for="emailInput" class="form-label"
                        >Email address <sup> <i class="bi bi-asterisk"></i></sup
                    ></label>
                    <div class="d-flex input-container">
                        <i class="bi bi-envelope icon"> </i>
                        <input
                            type="email"
                            class="input-field"
                            id="emailInput"
                            v-model="Three"
                        />
                    </div>
                </div>
                <div class="col-md-3 col-sm-4">
                    <label for="numberInput" class="form-label"
                        >Teléfono <sup> <i class="bi bi-asterisk"></i></sup
                    ></label>
                    <div class="d-flex input-container">
                        <i class="bi bi-telephone icon"></i>

                        <input
                            type="number"
                            class="input-field"
                            id="numberInput"
                            v-model="Four"
                        />
                    </div>
                </div>
            </div>
            <div class="row row-form">
                <div class="col-md-6 d-flex justify-content-center flex-wrap">
                    <label for="numberInput" class="form-label flex-grow-1"
                        >Áreas de interés laboral (mín. 1)
                        <sup> <i class="bi bi-asterisk"></i></sup
                    ></label>
                    <div class="d-flex input-container">
                        <i class="bi bi-list-stars icon"> </i>
                        <input
                            type="text"
                            class="input-field"
                            id="interestInput"
                            v-model="Five"
                        />
                    </div>
                    <div
                        v-for="n in counterInterest"
                        class="d-flex input-container"
                    >
                        <div class="flex-grow-1">
                            <formInputs
                                @decrease-by="(n) => counterInterest--"
                            ></formInputs>
                        </div>
                    </div>

                    <button
                        @click="counterInterest++"
                        type="button"
                        class="btn button-rounded rounded-circle"
                    >
                        <i class="bi bi-plus-lg"></i>
                    </button>
                </div>
                <div class="col-md-6 d-flex justify-content-center flex-wrap">
                    <label for="numberInput" class="form-label flex-grow-1"
                        >Hobbies (mín. 1)
                        <sup> <i class="bi bi-asterisk"></i></sup
                    ></label>

                    <div class="d-flex input-container">
                        <i class="bi bi-list-stars icon"></i>

                        <div class="input-group">
                            <input
                                type="text"
                                class="input-field"
                                id="hobbiesInput"
                                v-model="Six"
                                aria-describedby="button-addon2"
                            />
                        </div>
                    </div>

                    <div
                        v-for="n in counterHobbies"
                        class="d-flex input-container"
                    >
                        <div class="flex-grow-1">
                            <formInputs
                                @decrease-by="(n) => counterHobbies--"
                            ></formInputs>
                        </div>
                    </div>

                    <button
                        @click="counterHobbies++"
                        type="button"
                        class="btn button-rounded rounded-circle"
                    >
                        <i class="bi bi-plus-lg"></i>
                    </button>
                </div>
            </div>
            <div class="row">
                <div class="col d-flex justify-content-center">
                    <button
                        @click="toggleModal"
                        class="btn rounded-pill button-save"
                    >
                        Generar texto
                    </button>
                </div>
            </div>
        </div>
        <FooterLayout></FooterLayout>
    </AuthenticatedLayout>
</template>

<script>
export default {
    components: {
        FormInputs,
        ModalText2,
    },
};
</script>
