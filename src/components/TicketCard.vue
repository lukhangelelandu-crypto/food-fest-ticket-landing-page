<template>
    <div :class="['ticket-card', { featured }]">
        <h2>{{ name }}</h2>
        <p class="price">{{ price }}</p>
        <ul>
            <li v-for="(benefit, i) in benefits" :key="i">{{ benefit }}</li>
        </ul>

        <!-- Favourite -->
        <button @click="toggleFavourite" class="Fav-btn">
            <span v-if="favourited">❤️</span>
            <span v-else>🤍</span> Favourite
        </button>

        <!-- Call to Action -->
        <button class="cta">Notify Me</button>
    </div>
</template>

<script>
export default {
    props: {
        name: String,
        price: String,
        benefits: Array,
        featured: Boolean
    },
    data() {
        return { 
            favourited: false 
        };
    },
    methods: {
        togglefavourite() {
            this.favourited = !this.favourited;
        }
    }
};
</script>

<style scoped>
.fav-btn {
    margin-top: 0.5rem;
    background: none;
    border: none;
    cursor: pointer;
    font-size: 1rem;
}
.fav-btn span {
    margin-right: 0.3rem;
}
.ticket-card {
    border: 1px solid #333;
    padding: 1rem;
    border-radius: 8px;
    transition: transform 0.3s, box-shadow 0.3s;
    background: #fff;
    width: 250px;
}
.ticket-card:hover {
    transform: scale(1.05);
    box-shadow: 0 4px 12px rgba(0,0,0,0,2);
}
.ticket-card h2 {
    color: #1976d2;
    font-weight: 700;
    margin-bottom: 0.5rem;
}
.ticket-card ul {
    margin: 0;
    padding-left: 1rem;
}
.ticket-card li {
    color: #444;
    font-size: 0.95rem;
    margin-bottom: 0.3rem;
}
.featured {
    border: 2px solid gold;
    background: #fffbea;
}
.price {
    font-weight: bold;
    color: #2e7d32;
}
.fav-btn {
    margin-top: 0.5rem;
    background: none;
    border: none;
    cursor: pointer;
    font-size: 1rem;
}
.cta {
    margin-top: 1rem;
    background: #ff5722;
    color: white;
    border: none;
    padding: 0.5rem 1rem;
    border-radius: 6px;
    cursor: pointer
}
cta:hover {
    background: #e64a19;
}
</style>