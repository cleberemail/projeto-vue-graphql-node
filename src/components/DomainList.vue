<template>
    <div id="main">
        <div class="container">
            <div class="row">
                <div class="col-md">
                    <app-item-list titulo="Prefixos" v-bind:items="prefixes" v-on:addItem="addPrefix" v-on:deleteItem="deletePrefix"></app-item-list>
                </div>

                <div class="col-md">
                    <app-item-list titulo="Sufixos" v-bind:items="sufixes" v-on:addItem="addSufix" v-on:deleteItem="deleteSufix"></app-item-list>
                </div>
            </div>
            <br>
            <h5>Dominios <span class="badge bg-info">{{ dominios.length }}</span></h5>
            <div class="card">
                <div class="card-body">
                    <ul class="list-group">
                        <li class="list-group-item" v-for="dominio in dominios" v-bind:key="dominio">{{ dominio }}</li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import AppItemList from "./AppItemList.vue";

export default {
    name: "App",
    components: {
        AppItemList
    },
    data: function () {
        return {
            prefixes: ["cleber", "barbara", "meg"],
            sufixes: ["lindo", "belo", "maravilhoso"]
        };
    },
    methods: {
        addPrefix(prefixo) {
            this.prefixes.push(prefixo);
        },
        addSufix(sufixo) {
            this.sufixes.push(sufixo);
        },
        deletePrefix(prefixo) {
            this.prefixes.splice(this.prefixes.indexOf(prefixo), 1);
        },
        deleteSufix(sufixo) {
            this.sufixes.splice(this.sufixes.indexOf(sufixo), 1);
        }
    },
    computed: {
        dominios() {
            const dominios = [];
            for (const prefix of this.prefixes) {
                for (const sufix of this.sufixes) {
                    dominios.push(prefix + " - " + sufix);
                }
            }
            return dominios;
        }
    }
};
</script>
