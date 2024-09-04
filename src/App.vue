<template>
    <div>
        <div class="language" @click="toggleLanguage">
            <span>Language</span>
            <span>{{ this.language }}</span>
        </div>
        <div class="zodiac-list">
            <ZodiacSign
                v-for="sign in zodiacSigns"
                :key="sign.name"
                :sign="sign"
                :language="language"
                @click="showDescription(sign)"
            />
        </div>
        <ZodiacDescription
            v-if="showDescriptionModal"
            :sign="selectedSign"
            :language="language"
            @close="hideDescriptionModal"
        />
    </div>
</template>

<script>
import ZodiacSign from './components/ZodiacSigns';
import ZodiacDescription from './components/ZodiacDescription.vue';
import zodiacData from './zodiacData.json';

export default {
    components: {
        ZodiacSign,
        ZodiacDescription
    },
    data() {
        return {
            zodiacSigns: zodiacData,
            showDescriptionModal: false,
            selectedSign: null,
            language: 'ru' // или 'en'
        }
    },
    methods: {
        showDescription(sign) {
            this.selectedSign = sign;
            this.showDescriptionModal = true;
        },
        hideDescriptionModal() {
            this.showDescriptionModal = false;
        },
        toggleLanguage() {
            this.language = this.language === 'ru' ? 'en' : 'ru';
        }
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
.zodiac-list {
    display: grid;
    grid-gap: 20px;
    grid-template-columns: 1fr 1fr;
}
.language {
    display: inline-block;
    align-items: center;
    justify-content: flex-end;
    padding: 10px;
    margin-bottom: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
    cursor: pointer;

}

.language span:first-child {
    margin-right: 5px;
}
</style>
