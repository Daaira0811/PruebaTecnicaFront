<script setup>
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import { Head } from "@inertiajs/vue3";
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
        <div class="container mt-3">
            <div class="row">
                <h2>Contacto</h2>
            </div>
            <div
                class="row mt-4 d-flex justify-content-start align-items-center text-align-center"
            >
                <div class="col-sm-1">
                    <i class="bi bi-person"></i>
                </div>
                <div class="col-sm-2 text-align-center">
                    <p>Daira Acuña carilao</p>
                </div>
            </div>
            <div class="row">
                <div class="col-sm-1"><i class="bi bi-geo"></i></div>
                <div class="col-sm-3">
                    <p>Araucania, Temuco</p>
                </div>
            </div>
            <div class="row">
                <div class="col-sm-1">
                    <i class="bi bi-telephone"></i>
                </div>
                <div class="col-sm-2">
                    <p>+569-58573893</p>
                </div>
            </div>
            <div class="row">
                <div class="col-sm-1">
                    <i class="bi bi-envelope"></i>
                </div>
                <div class="col-sm-2">
                    <p>daira.carilao@gmail.com</p>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
