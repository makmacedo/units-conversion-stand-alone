<template>
<main class="flex justify-center w-full p-8 mt-24 bg-gray-300">
  <div class="block">
    <div v-for="unit in weightUnits" :key="unit.symbol" class="w-64 p-2 my-auto">
      <label class="block mb-2 text-sm font-bold text-gray-700" for="kilogram">
        {{ unit.name }} ({{ unit.symbol }})
      </label>
      <input id="kilogram" type="number" v-model="unit.value" @change="convert(unit)" 
        class="w-full px-3 py-2 leading-tight text-gray-700 border rounded shadow appearance-none focus:outline-none focus:shadow-outline">
    </div>
  </div>    
</main>
</template>

<script>
export default {
  name: 'MainContent',

  data() {
    return {
      unitValue: 0,
      weightUnits: [
        { // Kilogram
          name: 'Kilograms', 
          symbol: 'Kg',
          toSI: 1,
          fromSI: 1,
          precision: 3,
          value: 0
        },
        { // Gram
          name: 'Grams',
          symbol: 'g',   
          toSI: 0.001,
          fromSI: 1000,
          precision: 3,
          value: 0,
        },
        { // Metric Tonne
          name: 'Metric Tonnes',
          symbol: 't',   
          toSI: 1000,
          fromSI: 0.001,
          precision: 6,
          value: 0,
        },
        { // Pound
          name: 'Pounds',
          symbol: 'lb',   
          toSI: 0.453592,
          fromSI: 2.20462,
          precision: 3,
          value: 0,
        },
        { // Ounce
          name: 'Ounces',
          symbol: 'oz',   
          toSI: 0.0283495,
          fromSI: 35.274,
          precision: 3,
          value: 0,
        }
      ]
    }
  },

  methods: {
    convert(baseUnit) {
      this.weightUnits.forEach(weightUnit => {
          weightUnit.value = this.round(baseUnit.value * baseUnit.toSI * weightUnit.fromSI, weightUnit.precision)
      })
    },

    round(value, precision) {
      let factorOfTen = Math.pow(10, precision)
      return Math.round(value * factorOfTen) / factorOfTen
    }
  }
}
</script>
