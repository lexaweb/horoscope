<template>
    <div class="zodiac-sign">
        <div class="zodiac-sign__title">
            <i :class="sign.icon">{{sign.icon}}</i>
            <h3>{{ sign.name[language] }}</h3>
        </div>
        <p>{{ sign.dates[language] }}</p>
    </div>
</template>

<script>
export default {
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
}
</script>


<style scoped>
i {
    margin-right: 10px;
    font-size: 40px;
}
.zodiac-sign {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 20px;
    border-radius: 10px;
    background: grey;
    cursor: pointer;
    transition: 0.3s;
}
.zodiac-sign:hover {
    opacity: 0.7;
}
.zodiac-sign__title {
    display: flex;
    align-items: center;
}
</style>
