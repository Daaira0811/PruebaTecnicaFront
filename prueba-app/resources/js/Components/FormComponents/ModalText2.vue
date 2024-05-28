<style scoped>
@import "../../../css/styles.css";
</style>
<template>
    <div class="modal-mask d-flex justify-content-center align-items-center">
        <div class="modal-wrapper">
            <div class="modal-container">
                <div class="card text-start">
                    <div class="card-header p-3 bg-white">
                        <h3>Texto generado</h3>
                    </div>
                    <div class="card-body">
                        <p class="card-text" ref="cardText">
                            {{ text.partOne }} {{ One }} {{ Two }}
                            {{ text.partTwo }} {{ Five }} {{ text.partThree }}
                            {{ Six }}. {{ text.partFour }} {{ Three }}
                            {{ text.partFive }} {{ Four }}{{ text.partSix }}
                        </p>
                    </div>
                    <div
                        class="d-flex card-footer justify-content-end bg-white"
                    >
                        <button
                            @click="copyText"
                            type="button"
                            class="btn buttons d-flex align-items-center justify-content-center"
                            style="background-color: #69bf8e"
                        >
                            <svg
                                xmlns="http://www.w3.org/2000/svg"
                                width="16"
                                height="16"
                                fill="currentColor"
                                class="bi bi-copy me-2"
                                viewBox="0 0 16 16"
                            >
                                <path
                                    fill-rule="evenodd"
                                    d="M4 2a2 2 0 0 1 2-2h8a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2zm2-1a1 1 0 0 0-1 1v8a1 1 0 0 0 1 1h8a1 1 0 0 0 1-1V2a1 1 0 0 0-1-1zM2 5a1 1 0 0 0-1 1v8a1 1 0 0 0 1 1h8a1 1 0 0 0 1-1v-1h1v1a2 2 0 0 1-2 2H2a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h1v1z"
                                />
                            </svg>
                            Copiar Texto
                        </button>
                        <button
                            style="background-color: #bf9d8a"
                            class="btn buttons"
                            @click="close"
                        >
                            Cerrar
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import * as Vue from "vue";

export default {
    props: {
        modalActive: {
            type: Boolean,
        },
        One: {
            type: String,
            // required: true,
            default: "Nombre",
        },
        Two: {
            type: String,
            // required: true,
            default: "Apellidos",
        },
        Three: {
            type: String,
            // required: true,
            default: "Correo",
        },
        Four: {
            type: String,
            // required: true,
            default: "Teléfono",
        },
        Five: {
            type: String,
            // required: true,
            default: "Áreas de interés laboral",
        },
        Six: {
            type: String,
            // required: true,
            default: "Hobbies",
        },
    },
    data() {
        return {
            text: {
                partOne: "¡Hola! Soy",
                partTwo:
                    "Me apasiona el aprendizaje y siempre busco nuevos desafíos. Disfruto colaborar en equipo, comunicarme eficazmente y encontrar soluciones creativas. Además de mi curiosidad, me interesa [el/la]",
                partThree:
                    "Creo en el impacto positivo y en aplicar mis habilidades en proyectos significativos. Fuera del trabajo, disfruto [el/la]",
                partFour:
                    "Soy una persona apasionada, curiosa y orientada a resultados. ¡Lista para enfrentar nuevos retos con entusiasmo! Puedes contactarme a través de",
                partFive: " o por teléfono al",
                partSix: ". ¡Espero conocerte pronto!",
            },
        };
    },
    setup(props, { emit }) {
        const cardText = Vue.ref(null);
        const close = () => {
            emit("close");
        };
        const copyText = () => {
            if (cardText.value) {
                navigator.clipboard.writeText(cardText.value.textContent);
            }
        };
        return { close, copyText, cardText };
    },
};
</script>
