<template>

    <div>
        <div id="slogan" class="text-center">
            <h1>Teste <span class="fa fa-check"></span></h1>
            <h6 class="text-secondary">Gerador de nomes utilizando vue.js, graphql e node</h6>
        </div>
    </div>

    <div id="main">
        <domain-list></domain-list>
    </div>

</template>

<script>
import "bootstrap/dist/css/bootstrap.min.css";
import "font-awesome/css/font-awesome.min.css";
import DomainList from "@/components/DomainList.vue";

export default {
    name: "App",
    components: {
        DomainList
    }
};
</script>

<style>
    #slogan {
        margin: 30px 0px;
    }

    #main {
        background: #EEE;
        padding: 30px 0px;
    }
</style>
