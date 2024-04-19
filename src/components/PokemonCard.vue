<script>
import { store } from '../store.js';
export default {
    props: {
        cardInfo: Object
    },
    data() {
        return {
            store,
            wicons :[
                {
                    'text': 'Bug',
                    'icon': '🐞'
                },
                {
                    'text': 'Dark',
                    'icon': '🌙'
                },
                {
                    'text': 'Dragon',
                    'icon': '🐲'
                },
                {
                    'text': 'Electric',
                    'icon': '⚡'
                },
                {
                    'text': 'Fairy',
                    'icon': '✨'
                },
                {
                    'text': 'Fighting',
                    'icon': '🥊'
                },
                {
                    'text': 'Fire',
                    'icon': '🔥'
                },
                {
                    'text': 'Flying',
                    'icon': '🌪️'
                },
                {
                    'text': 'Ghost',
                    'icon': '👻'
                },
                {
                    'text': 'Grass',
                    'icon': '🌿'
                },
                {
                    'text': 'Ground',
                    'icon': '🗿'
                },
                {
                    'text': 'Ice',
                    'icon': '❄️'
                },
                {
                    'text': 'Poison',
                    'icon': '☠️'
                },
                {
                    'text': 'Psychic',
                    'icon': '🧠'
                },
                {
                    'text': 'Rock',
                    'icon': '⛰️'
                },
                {
                    'text': 'Steel',
                    'icon': '🛡️'
                },
                {
                    'text': 'Water',
                    'icon': '💧'
                }
            ],
        }

    },
    methods: {
        getWeaknessIcon(weakText) {
            // let iconsList = [];
            // for (let index = 0; index < this.wicons.length; index++) {
            //     const element = this.wicons[index];
            //     if (this.cardInfo.weaknesses.includes(element.text)) {
            //         iconsList.push(element.icon) 
            //     }
            // }
            // return iconsList.join(' ')
            return this.wicons.filter((v)=>v.text == weakText)[0].icon;
        }
    }
}
</script>

<template>
    <li class="list-group-item col-2">
        <div class="card">
            <div class="card-body">
                <div class="content d-flex flex-column">
                    <span class="fw-bold">{{ cardInfo.name }}</span>
                    <div class="img-cnt d-flex justify-content-center align-items-center">
                        <img :src="cardInfo.img" alt="">
                    </div>
                </div>
                <div class="special-badge badge my-2">
                    Weight: {{ cardInfo.weight }} , Height: {{ cardInfo.height }}
                </div>
                <div class="py-2">
                    <span class="me-2 badge bg-secondary" v-for="singleType in cardInfo.type">{{ singleType }}</span>
                </div>
                <div class="py-2">
                    <span class="ps-2 weaknesses" v-for="weak in cardInfo.weaknesses">
                        {{ getWeaknessIcon(weak) }}
                    </span>
                </div>
            </div>
        </div>
    </li>
</template>

<style></style>