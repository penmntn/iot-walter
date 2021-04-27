<script>
import { defineComponent } from 'vue'
import { Line } from 'vue3-chart-v2'

export default defineComponent({
  name: 'Estadisticas Diarias',
  extends: Line,
  props: {
    Sensor1: { type: Array },
    Sensor2: { type: Array },
    Sensor3: { type: Array },
    Sensor4: { type: Array },
    Sensor5: { type: Array },
    valMax: { type: Array },
    horas: { type: Array }

  },
  watch: {
    horas () {
      this.$data._chart.update()
    }
  },
  mounted () {
    this.renderChart({
      labels: this.horas,
      datasets: [
        {
          label: 'sensor1',
          borderColor: 'red',
          data: this.Sensor1

        },
        {
          label: 'sensor2',
          borderColor: 'blue',
          data: this.Sensor2

        },
        {
          label: 'sensor3',
          borderColor: 'green',
          data: this.Sensor3

        },

        {
          label: 'sensor4',
          borderColor: 'orange',
          data: this.Sensor4

        },
        {
          label: 'sensor5',
          borderColor: 'black',
          data: this.Sensor5

        },
        {
          label: 'Mayor',
          borderColor: 'purple',
          data: this.valMax
        }

      ]
    })
  }
})
</script>
