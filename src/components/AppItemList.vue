<template>
  <div>
      <h5>{{ titulo }} <span class="badge bg-info">{{ items.length }}</span></h5>
      <div class="card">
          <div class="card-body">
              <ul class="list-group">
                  <li class="list-group-item" v-for="item in items" v-bind:key="item">
                      <div class="row">
                          <div class="col-md">
                              {{ item }}
                          </div>
                          <div class="col-md text-end">
                              <button class="btn btn-sm" v-on:click="deleteItem(item)"><span class="fa fa-trash"></span></button>
                          </div>
                      </div>
                  </li>
              </ul>
              <br/>
              <div class="input-group">
                  <input class="form-control" type="text" placeholder="Digite o item" v-model="itemDigitado" v-on:keyup.enter="addItem(itemDigitado)">
                  <div class="input-group-append">
                      <button class="btn btn-info rounded-0" v-on:click="addItem(itemDigitado)"><span class="fa fa-plus"></span></button>
                  </div>
              </div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
    name: "AppItemList",
    props: ["titulo", "items"],
    data() {
        return {
            itemDigitado: ""
        };
    },
    methods: {
        addItem(item) {
            this.$emit("addItem", item);
            this.itemDigitado = "";
        },
        deleteItem(item) {
            this.$emit("deleteItem", item);
        }
    }
};
</script>
