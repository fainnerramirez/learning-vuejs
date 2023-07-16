<script setup>
    defineProps(
        [
            "name",
            "image",
            "species"
        ]
    )
</script>

<template>
    <div class="card" style="margin: 10px; width: 18rem;">
        <img :src="image" class="card-img-top" :alt="name">
        <div class="card-body">
            <p class="card-text">
                {{ name }} - {{ species }}
            </p>
        </div>
    </div>
</template>