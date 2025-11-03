<h1 align="center"> <img src="https://readme-typing-svg.demolab.com?color=0D7FFFC5&lines=print(%22Hello%2C+Word%22);%E4%B8%94%E8%A1%8C%E4%B8%94%E5%BF%98%E4%B8%94%E9%9A%8F%E9%A3%8E%EF%BC%8C%E4%B8%94%E5%90%AC%E4%B8%94%E7%9C%8B%E4%B8%94%E4%BB%8E%E5%AE%B9&center=true&size=27&font=Fira+Code" alt="Typing SVG" /> </h1>

<div class="container">

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

<div id="lang-card" class="card">
    <div class="chart-container">
      <canvas id="eventChart"></canvas>
    </div>
    <div class="chart-container">
      <canvas id="langChart"></canvas>
    </div>
</div>

## My Skills



<p align="center">
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=java,kotlin,js,ts,gradle,spring,nodejs,vue,nuxtjs,rabbitmq,pinia,mysql,redis,git,docker,vscode,idea,obsidian&perline=9" />
  </a>
</p>



</div>

<!-- 全局样式 -->

<style>
/* 页面背景与容器 */
body.page-about {
  background: #f7f9fc;
  color: #34414e;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  line-height: 1.6;
  padding: 2rem 1rem;
}
.page-about .container {
  max-width: 800px;
  margin: 0 auto;
  padding: 0 1rem;
}
 /* 标题风格 */
.page-about h1, .page-about h2, .page-about h3 {
  color: #1e2a38;
  margin-bottom: 1rem;
}
.page-about h1 { font-size: 2.5rem; }
.page-about h2 { font-size: 2rem; margin-top: 2rem; }
.page-about h3 { font-size: 1.5rem; margin-top: 1.5rem; }
/* 段落与留白 */
.page-about p {
  margin-bottom: 1.25rem;
}

/* 卡片公用 */
.card {
  background: linear-gradient(145deg, #ffffff, #f0f4fa);
  border-radius: 1rem;
  box-shadow: 0 8px 16px rgba(0,0,0,0.06);
  padding: 1.5rem;
  margin-bottom: 2rem;
  transition: transform .2s, box-shadow .2s;
}
.card:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 24px rgba(0,0,0,0.10);
}

/* 个人简介卡片 */
#intro-card {
  text-align: center;
}
#intro-card img {
  width: 120px;
  height: 120px;
  border-radius: 50%;
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  margin-bottom: 1rem;
}

/* GitHub 事件 & 语言统计 卡片 */
.chart-container {
  position: relative;
  height: 300px;
  margin-top: 1rem;
}

/* Total Commits 样式 */
.total-commits {
  margin-top: 1rem;
  font-weight: 600;
  color: #526e7a;
}

/* 列表微交互 */
.repo-list li, #event-stats li, #lang-stats li {
  padding: .5rem;
  border-radius: .5rem;
  transition: background .2s;
}
.repo-list li:hover,
#event-stats li:hover,
#lang-stats li:hover {
  background: rgba(66,165,245,0.1);
}

/* 响应式 */
@media (max-width: 600px) {
  .card { padding: 1rem; }
  .page-about h1 { font-size: 2rem; }
}
</style>



<!-- 引入 Chart.js -->

<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<script>
;(async () => {
  const username = 'handi404';
  // 绘制事件 Doughnut
  const ctx1 = document.getElementById('eventChart').getContext('2d');
  new Chart(ctx1, {
    type: 'doughnut',
    data: {
      labels: Object.keys(eventCounts),
      datasets: [{
        data: Object.values(eventCounts),
        backgroundColor: [
          'rgba(66,165,245,0.8)',
          'rgba(102,187,106,0.8)',
          'rgba(255,202,40,0.8)',
          'rgba(239,83,80,0.8)',
          'rgba(171,71,188,0.8)'
        ],
        hoverOffset: 10
      }]
    },
    options: {
      cutout: '60%',
      plugins: {
        legend: { position: 'bottom', labels: { boxWidth:12, padding:16 } }
      },
      maintainAspectRatio: false
    }
  });

  // —— 2. 拉取所有公开仓库 & 语言统计 ——  
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
        data: Object.values(langCounts),
        backgroundColor: 'rgba(66,165,245,0.8)'
      }]
    },
    options: {
      indexAxis: 'y',
      scales: {
        x: { beginAtZero: true, ticks: { callback: v => v } }
      },
      plugins: {
        legend: { display: false }
      },
      maintainAspectRatio: false
    }
  });

})();
</script>



<!-- 引入 Chart.js -->

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















