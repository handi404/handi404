<h1 align="center"> <img src="https://readme-typing-svg.demolab.com?color=0D7FFFC5&lines=print(%22Hello%2C+World%22);%E4%B8%94%E8%A1%8C%E4%B8%94%E5%BF%98%E4%B8%94%E9%9A%8F%E9%A3%8E%EF%BC%8C%E4%B8%94%E5%90%AC%E4%B8%94%E7%9C%8B%E4%B8%94%E4%BB%8E%E5%AE%B9&center=true&size=27&font=Fira+Code" alt="Typing SVG" /> </h1>



## Hi，👋



<!-- snake --> 

<p align="center">
<a href="https://github.com/handi404"><img src="https://img.shields.io/badge/GitHub-handi404-blue?logo=github" /></a>
<a href="https://blog.guoqi.dev/"><img src="https://img.shields.io/badge/Hexo_Blog-博客-yellow" /></a>
</p>

  <picture>  
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/handi404/handi404/refs/heads/output/github-snake-dark.svg" />  
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/handi404/handi404/refs/heads/output/github-snake.svg" />  
    <img alt="github-snake" src="https://raw.githubusercontent.com/handi404/handi404/refs/heads/output/github-snake-dark.svg" /> 
  </picture>



## My GitHub

<div align="center">
      <table style="width:100%;">
        <tr>
      	  <!-- 第一个图片 -->
      	  <td align="center">
            <img height='200' src="https://github-readme-stats.vercel.app/api?username=handi404&show_icons=true&theme=tokyonight" />
          </td>
          <!-- 第二个图片 -->
          <td align="center">
            <img height='200' src="https://github-readme-stats.vercel.app/api/top-langs/?username=handi404&layout=compact&theme=tokyonight" />
          </td>
        </tr>
          <!-- 第三个图片 -->
        <tr>
          <td colspan="2" align="center">
            <img height="220" src="https://github-readme-activity-graph.vercel.app/graph?username=handi404&theme=github-compact&hide_border=true&area=true" />
          </td>
        </tr>
      </table>
    </div>



## My Skills



<p align="center">
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=java,kotlin,js,ts,gradle,spring,nodejs,vue,nuxtjs,rabbitmq,pinia,mysql,redis,git,docker,vscode,idea,obsidian&perline=9" />
  </a>
</p>





<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<script>
;(async () => {
  const username = 'handi404';
  // —— 1. 拉取最近 30 条公开事件，汇总各类型数量 ——  
  let res = await fetch(`https://api.github.com/users/${username}/events/public?per_page=30`);
  const events = res.ok ? await res.json() : [];
  const eventCounts = {};
  events.forEach(e => eventCounts[e.type] = (eventCounts[e.type]||0) + 1);
  // 绘制 Doughnut 图
  const ctx1 = document.getElementById('eventChart').getContext('2d');
  new Chart(ctx1, {
    type: 'doughnut',
    data: {
      labels: Object.keys(eventCounts),
      datasets: [{
        data: Object.values(eventCounts),
        backgroundColor: [
          '#4caf50','#03a9f4','#ff9800','#f44336','#9c27b0',
          '#2196f3','#ffc107','#795548','#607d8b','#e91e63'
        ]
      }]
    },
    options: {
      plugins: {
        title: {
          display: true,
          text: 'Recent GitHub Events'
        },
        legend: {
          position: 'right'
        }
      },
      maintainAspectRatio: false
    }
  });
  // —— 2. 拉取所有公开仓库，统计主语言分布 ——  
  let repos = [], page = 1;
  while (true) {
    res = await fetch(`https://api.github.com/users/${username}/repos?per_page=100&page=${page}`);
    const batch = res.ok ? await res.json() : [];
    if (!batch.length) break;
    repos = repos.concat(batch);
    page++;
  }
  const langCounts = {};
  repos.forEach(r => {
    const lang = r.language || 'Unknown';
    langCounts[lang] = (langCounts[lang]||0) + 1;
  });
  // 绘制水平条形图
  const ctx2 = document.getElementById('langChart').getContext('2d');
  new Chart(ctx2, {
    type: 'bar',
    data: {
      labels: Object.keys(langCounts),
      datasets: [{
        label: '仓库数',
        data: Object.values(langCounts),
        backgroundColor: '#42a5f5'
      }]
    },
    options: {
      indexAxis: 'y',
      plugins: {
        title: {
          display: true,
          text: 'Programming Languages Usage'
        },
        legend: { display: false }
      },
      scales: {
        x: {
          beginAtZero: true,
          ticks: {
            callback: v => v + ' 个'
          }
        }
      },
      maintainAspectRatio: false
    }
  });
})();
</script>















