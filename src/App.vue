<template>
  <table
    class="table is-bordered is-striped is-narrow is-hoverable is-fullwidth"
  >
    <thead>
      <tr>
        <th>Numbers</th>
        <th>Strings</th>
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
        { string: "two", number: 2 },
        { string: "One", number: 1 },
        { string: "Four", number: 4 },
        { string: "three", number: 3 },
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
