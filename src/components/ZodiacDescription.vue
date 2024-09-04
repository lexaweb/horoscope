<template>
<!--    v-if="show"-->
    <div class="modal" >
        <h2>{{ sign.name[language] }}</h2> <p>{{ sign.description[language] }}</p>
        <button @click="$emit('close')">Назад (Back)</button>

    </div>
</template>

<script>
export default {
    name: "ZodiacDescription.vue",
    props: {
        sign: {
            type: Array,
            required: true,
        },
        language: {
            type: String,
            default: "ru",
        },
    },
    data() {
        return {
        };
    },

};
</script>

<style scoped>
.modal {
    position: fixed;
    top: 50%;
    left: 50%;
    width: 90%;
    transform: translate(-50%, -50%);
    background-color: white;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;

z-index: 10;
    text-align: center;
}

.modal h2 {
    margin-bottom: 15px;
}

.modal button {
    background-color: #4CAF50; /* Green */
    border: none;
    color: white;
    padding: 10px 20px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
    border-radius: 5px;
}


button:hover {
    background-color: #45a049;
}
</style>