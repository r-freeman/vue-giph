<template>
    <b-card-group columns>
        <b-card
                v-for="gif in gifs"
                :key="gif.id"
                :img-src="gif.images.fixed_width.url"
                :img-alt="gif.title">
            <b-card-text>
                <a :href="gif.url" target="_blank">{{gif.title}}</a>
            </b-card-text>
        </b-card>
    </b-card-group>
</template>

<script>
    import axios from "axios";

    const GIPHY_URL = "https://api.giphy.com/v1/gifs";
    const API_KEY = "R6P40k3DHUF3FoJzz3GMf2WgdKD2eaI7";

    export default {
        name: "GiphyViewer",
        components: {},
        data() {
            return {
                gifs: []
            }
        },
        mounted() {
            axios
                .get(`${GIPHY_URL}/trending?api_key=${API_KEY}`)
                .then(res => {
                    this.gifs = res.data.data
                })
        },
        methods: {}
    }
</script>

<style scoped>

</style>
