# Dashboardpagejs
Criação de dashboard 
// Importa a biblioteca Chart.js
import Chart from 'chart.js';

// Cria o contexto do canvas para o gráfico
const ctx = document.getElementById('myChart').getContext('2d');

// Cria o gráfico
const chart = new Chart(ctx, {
  type: 'bar',
  data: {
    labels: ['Janeiro', 'Fevereiro', 'Março'],
    datasets: [{
      label: 'Vendas',
      data: [100, 200, 300],
      backgroundColor: [
        'rgba(255, 99, 132, 0.2)',
        'rgba(54, 162, 235, 0.2)',
        'rgba(255, 206, 86, 0.2)'
      ],
      borderColor: [
        'rgba(255, 99, 132, 1)',
        'rgba(54, 162, 235, 1)',
        'rgba(255, 206, 86, 1)'
      ],
      borderWidth: 1
    }]
  },
  options: {
    scales: {
      yAxes: [{
        ticks: {
          beginAtZero: true
        }
      }]
    }
  }
});

// Cria a tabela
const tabela = document.getElementById('tabela');
const dados = [
  { mes: 'Janeiro', vendas: 100 },
  { mes: 'Fevereiro', vendas: 200 },
  { mes: 'Março', vendas: 300 }
];

tabela.innerHTML = `
  <table>
    <thead>
      <tr>
        <th>Mês</th>
        <th>Vendas</th>
      </tr>
    </thead>
    <tbody>
      ${dados.map(dado => `
        <tr>
          <td>${dado.mes}</td>
          <td>${dado.vendas}</td>
        </tr>
      `).join('')}
    </tbody>
  </table>
`;
