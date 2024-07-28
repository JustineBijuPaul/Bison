<template>
    <div class="banner">
        <section class="home">
            <div class="description">
                <h1 class="title">
                    <span class="gradient-text">Cleanliness, Naturally.</span> <br> with the Best
                </h1>
                <p class="paragraph">
                    In a world filled with opportunities, having a mentor can make all the
                    difference. Explore why people turn to this invaluable resource to
                    unlock their potential.
                </p>
                <form id="form" autocomplete="off">
                    <input type="email" id="email-id" name="email_address" aria-label="email adress" placeholder=""
                        required oninput="checkEmpty()" />
                    <button type="submit" class="btn" aria-label="submit">
                        <span>Subscribe</span>
                        <!-- Use a different icon library or register ion-icon -->
                        <i class="fas fa-arrow-right"></i>
                    </button>
                </form>
            </div>

            
        </section>

    </div>
</template>

<style scoped></style>

<script>
import ScrollReveal from "scrollreveal";
import VanillaTilt from "vanilla-tilt";

export default {
    mounted() {
        // Initialize ScrollReveal
        ScrollReveal().reveal(".title", {
            delay: 300,
            origin: "top",
        });

        ScrollReveal().reveal(".paragraph", {
            delay: 800,
            origin: "top",
        });

        ScrollReveal().reveal("#form", {
            delay: 1200,
            origin: "bottom",
        });

        // Initialize VanillaTilt
        VanillaTilt.init(document.querySelectorAll("[data-tilt]"));
    },
};
</script>