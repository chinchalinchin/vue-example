<template>
    <RouterLink id="icon-link-wrapper"
        :to="route"
        v-if="this.config.link">
        <img :id="this.id"
            :alt="this.alt"
            :class="{
                'control': this.config.control
            }"
            :src="`src/assets/svg/${icon}.svg`"
            :style="{
                'width': this.dimensions.width, 
                'height': this.dimensions.height
            }"
            :tabindex="focusable ? 1 : -1"
            />
    </RouterLink>
</template>

<script>
import { RouterLink } from "vue-router";

export default {
    computed: {

    },
    methods: {

    },
    props: {
        alt: {
            Type: String,
            default: 'Icon'
        },
        config: {
            Type: Object,
            default: {
                control: true,
                link: true
            }
        },
        dimensions: {
            Type: Object,
            default: {
                width: '32px',
                height: '32px'
            } 
        },
        focusable: {
            Type: Boolean,
            default: true
        },
        icon: {
            Type: String,
            default: 'meal_coffee_cup'
        },
        id: {
            Type: String,
            default: 'icon'
        },
        route: {
            Type: String,
            default: ''
        }
    }
}
</script>

<style scoped>
.control {
    border-radius: 55px;
    box-shadow: var(--shadow-control) var(--shadow-control) 10px black;
}
img:focus,
img:hover{
    transform: scale(1.15);
    -webkit-filter: brightness(1.15);
    -moz-filter: brightness(1.15);
    -ms-filter: brightness(1.15);
    filter: brightness(1.15);
}
</style>