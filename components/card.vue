<template>
    <v-card hover @click.native='click'>
        <v-card-title>
            <div class='number white--text'>
                {{ item.rank }}
            </div>
            <v-img :src='item.image' aspect-ratio='0.83'/>
        </v-card-title>
        <v-card-text class='font-weight-black'>
            <p>{{ item.name }}</p>
            <p class='blue-grey--text lighten-4'>
                {{ item.pos }}
            </p>
        </v-card-text>
    </v-card>
</template>

<script>
export default {
    props: {
        item: {}
    },
    methods: {
        click() {
            this.$emit('click-card', this.item)
        }
    }
}
</script>
