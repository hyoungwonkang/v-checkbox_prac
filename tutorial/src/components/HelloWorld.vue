<template>
  <v-data-table
    v-model="selected"
    :headers="headers"
    :items="desserts"
    item-key="postno"
    class="elevation-1"
    single-select
    disable-sort
    @click:row="clickRow"
  >
    <template v-slot:[`item.postno`]="{ isSelected }">
      <v-checkbox :value="isSelected" @change="select($event)"></v-checkbox>
    </template>
  </v-data-table>
</template>

<script>
export default {
  data() {
    return {
      selected: [],
      disabledCount: 0,
      headers: [
        { text: "", value: "postno" },
        { text: "Dessert (100g serving)", align: "start", value: "name" },
        { text: "Calories", value: "calories" },
        { text: "Fat (g)", value: "fat" },
        { text: "Carbs (g)", value: "carbs" },
        { text: "Protein (g)", value: "protein" },
        { text: "Iron (%)", value: "iron" },
      ],
      desserts: [
        {
          name: "Frozen Yogurt",
          calories: 159,
          fat: 6.0,
          carbs: 24,
          protein: 4.0,
          iron: "1%",
          postno: 1,
        },
        {
          name: "Ice cream sandwich",
          calories: 237,
          fat: 9.0,
          carbs: 37,
          protein: 4.3,
          iron: "1%",
          postno: 2,
        },
        {
          name: "Eclair",
          calories: 262,
          fat: 16.0,
          carbs: 23,
          protein: 6.0,
          iron: "7%",
          postno: 3,
        },
        {
          name: "Cupcake",
          calories: 305,
          fat: 3.7,
          carbs: 67,
          protein: 4.3,
          iron: "8%",
          postno: 4,
        },
        {
          name: "Gingerbread",
          calories: 356,
          fat: 16.0,
          carbs: 49,
          protein: 3.9,
          iron: "16%",
          postno: 5,
        },
        {
          name: "Jelly bean",
          calories: 375,
          fat: 0.0,
          carbs: 94,
          protein: 0.0,
          iron: "0%",
          postno: 6,
        },
        {
          name: "Lollipop",
          calories: 392,
          fat: 0.2,
          carbs: 98,
          protein: 0,
          iron: "2%",
          postno: 7,
        },
        {
          name: "Honeycomb",
          calories: 408,
          fat: 3.2,
          carbs: 87,
          protein: 6.5,
          iron: "45%",
          postno: 8,
        },
        {
          name: "Donut",
          calories: 452,
          fat: 25.0,
          carbs: 51,
          protein: 4.9,
          iron: "22%",
          postno: 9,
        },
        {
          name: "KitKat",
          calories: 518,
          fat: 26.0,
          carbs: 65,
          protein: 7,
          iron: "6%",
          postno: 10,
        },
      ],
    };
  },
  created() {},
  methods: {
    select(e) {
      console.log(e);
    },
    clickRow(item, row) {
      row.select(true);
      console.log(item);
    },
    // selectAllToggle(props) {
    //   if (this.selected.length != this.desserts.length - this.disabledCount) {
    //     this.selected = [];
    //     const self = this;
    //     props.items.forEach((item) => {
    //       if (!item.disabled) {
    //         self.selected.push(item);
    //       }
    //     });
    //   } else this.selected = [];
    // },
  },
};
</script>
