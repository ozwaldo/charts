<template>
  <div id="content">
    <canvas ref="chart"></canvas>
  </div>
</template>
<script>
import Chart from 'chart.js';
export default {
  name: 'app',
  mounted() {
    var chart = this.$refs.chart;
    var context = chart.getContext("2d");
    var Grafica = new Chart(context, {
      type: 'line',
      data: {
        labels: ['Sistemas','Informática','Electronica','Industrial'],
        datasets:[{
          label: 'Estudiantes 2017',
          backgroundColor: 'rgb(255,159,64)',
          borderColor: 'rgb(255,159,64)',
          data: [360, 30, 125,350],
          fill: false
        },
        {
            label: 'Estudiantes 2018',
            backgroundColor: 'rgb(201,203,207)',
            borderColor: 'rgb(201,203,207)',
            data: [400,20,130,380],
            fill: false
        }]
      },
      options: {
        title: {
          display: true,
          text: 'Alumnos de Carreras Itsur'
        },
        scales: {
          xAxes: [{
            display:true,
            scaleLabel: {
              display: true,
              labelString: 'Carreras'
            }
          }],
          yAxes: [{
            display:true,
            scaleLabel: {
              display: true,
              labelString: 'Número de Estudiantes'
            }
          }]
        }
      }
    });
  }
}
</script>
