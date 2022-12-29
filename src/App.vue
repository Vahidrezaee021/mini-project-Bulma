<template>
  <table
    class="table is-bordered is-striped is-narrow is-hoverable is-fullwidth"
  >
    <thead>
      <tr>
        <th>Numbers</th>
        <th>Names</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="item in items" :key="item.index">
        <td>{{ item.number }}</td>
        <td>{{ item.string }}</td>
      </tr>
    </tbody>
  </table>
  <button class="button is-dark ml-5" @click="sortNumbers">Sort</button>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      items: [
        { string: "John", number: 18 },
        { string: "Sarah", number: 17.75 },
        { string: "Tom", number: 9.5 },
        { string: "Ali", number: 11.25 },
        { string: "Jerry", number: 13 },
        { string: "Matt", number: 5.5 },
        { string: "Patt", number: 20 },
        { string: "Khan", number: 19 },
      ],
      descNumbers: false,
    };
  },
  methods: {
    sortNumbers() {
      if (this.descNumbers) {
        this.descNumbers = false;
        this.items.sort((a, b) => {
          return a.number - b.number;
        });
      } else {
        this.descNumbers = true;
        this.items.sort((a, b) => {
          return b.number - a.number;
        });
      }
    },
  },
};
</script>
