<template>
    <v-container grid-list-sm text-xs-center>
        <v-layout row wrap>
            <v-flex xs2 align-end class='text-md-left'>
                <v-card-text class='font-weight-bold blue-grey--text lighten-2'>
                    Jump to Player
                </v-card-text>
            </v-flex>
            <v-flex xs4>
            <v-text-field solo placeholder='Search'
                v-model='search' @input='extractItems'/>
            </v-flex>
        </v-layout>
        <v-layout row wrap>
            <v-flex xs3 v-for='(item, index) in viewItems'
                :key='getIndexStr(index)'>
                <card :item='item' @click-card='click'/>
            </v-flex>
        </v-layout>
        <v-dialog v-model='modal'>
            <v-card>
                <v-layout>
                    <v-flex xs2>
                        <v-img :src='selectItem.image' aspect-ratio='0.9'/>
                    </v-flex>
                    <v-flex xs10>
                        <v-card-title>
                            <div>
                                <p class='font-weight-bold'>{{ selectItem.name }} | {{ selectItem.team }} | Rank: {{ selectItem.rank }}</p>
                                <div class='align-left'>
                                    <p>{{ selectItem.description }}</p>
                                </div>
                            </div>
                        </v-card-title>
                    </v-flex>
                </v-layout>
            </v-card>
        </v-dialog>
    </v-container>
</template>

<script>
import json from '~/assets/data.json'
import card from '~/components/card'

const data = json['data']

export default {
    data() {
        return {
            items: [],
            viewItems: [],
            search: '',
            modal: false,
            selectItem: {}
        }
    },
    components: {
        card
    },
    created() {
        this.items = data
        this.viewItems = this.items
    },
    methods: {
        getIndexStr(index) {
            return String(index)
        },
        extractItems() {
            const self = this
            let exItems = []
            self.items.forEach(item => {
                const name = item.name
                if (name.indexOf(self.search) != -1) {
                    exItems.push(item)
                }
            })
            self.viewItems = exItems
        },
        click(item) {
            this.selectItem = item
            this.modal = true
        }
    }
}
</script>

<style>
.number {
    background-color: #030b52;
    border: 3px solid #fff;
    border-radius: 50%;
    font-size: 16px;
    height: 36px;
    left: 31px;
    line-height: 30px;
    position: absolute;
    top: 31px;
    width: 36px;
    z-index: 1;
}
</style>
