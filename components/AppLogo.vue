<template>
  <div>
    <multi-select
      v-model="values"
      search
      :options="options"
      :filters="filters"
      :btnLabel="btnLabel"
      :selectOptions="data" />
  </div>
</template>

<script>

import multiSelect from 'vue-multi-select';
import 'vue-multi-select/dist/lib/vue-multi-select.min.css';

export default {
  data() {
    return {
      btnLabel: 'A simple vue multi select',
      name: 'first group',
      values: [],
      data: [{
        name: 'first group',
        list: [
          { name: '0' },
          { name: '2' },
          { name: '3' },
          { name: '8' },
          { name: '9' },
          { name: '11' },
          { name: '13' },
          { name: '14' },
          { name: '15' },
          { name: '18' },
        ],
      }, {
        name: 'second group',
        list: [
          { name: '21' },
          { name: '22' },
          { name: '24' },
          { name: '27' },
          { name: '28' },
          { name: '29' },
          { name: '31' },
          { name: '33' },
          { name: '35' },
          { name: '39' },
        ],
      }],
      filters: [{
        nameAll: 'select <= 10',
        nameNotAll: 'Deselect <= 10',
        func: (elem) => {
          if (elem.name <= 10) {
            return true;
          }
          return false;
        },
      }, {
        nameAll: 'Select contains 2',
        nameNotAll: 'Deselect contains 2',
        func: (elem) => {
          if (elem.name.indexOf('2') !== -1) {
            return true;
          }
          return false;
        },
      }],
      options: {
        renderTemplate: (elem) => `number : ${elem.name}`,
        multi: true,
        groups: true,
      },
    };
  },
  methods: {
  },
  components: {
    multiSelect,
  },
};
</script>
