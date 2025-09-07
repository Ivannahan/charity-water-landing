# charity-water-landing
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>charity: water — 校园行动 Landing Page</title>
  <meta name="description" content="与大学生建立联系，激励他们采取行动应对全球水危机的品牌化落地页。" />

  <!-- Font: Lato -->
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Lato:wght@300;400;700;900&display=swap" rel="stylesheet">

  <style>
    :root{
      --yellow:#F7C948;        /* Primary */
      --charcoal:#323232;      /* Headline / Body */
      --white:#ffffff;         /* Background / Text on dark */
      --ink:#111111;           /* Deep text */
      --sky:#f5f7fb;           /* Soft background tint */
      --accent:#0d6efd;        /* Link focus outline (a11y) */
      --radius-xl:1.25rem;     /* 20px */
      --radius-lg:0.875rem;    /* 14px */
      --shadow:0 10px 30px rgba(0,0,0,.08);
      --shadow-press:0 6px 18px rgba(0,0,0,.12);
      --maxw:1200px;
    }

    /* Base */
    html,body{height:100%}
    body{
      margin:0; font-family:"Lato",system-ui,-apple-system,Segoe UI,Roboto,"Helvetica Neue",Arial,"Noto Sans",sans-serif;
      color:var(--charcoal); background:var(--white);
      line-height:1.6; -webkit-font-smoothing:antialiased; text-rendering:optimizeLegibility;
    }
    img{max-width:100%; height:auto; display:block}
    a{color:inherit; text-decoration:none}
    .container{max-width:var(--maxw); margin-inline:auto; padding:0 20px}

    /* Buttons */
    .btn{display:inline-flex; gap:.5rem; align-items:center; justify-content:center; cursor:pointer; border:none; border-radius:999px; font-weight:700; letter-spacing:.2px; padding:.9rem 1.25rem; transition:transform .15s ease, box-shadow .2s ease, background-color .2s ease;}
    .btn-primary{background:var(--yellow); color:#1a1a1a; box-shadow:var(--shadow)}
    .btn-primary:hover{transform:translateY(-1px); box-shadow:var(--shadow-press)}
    .btn-outline{background:transparent; border:2px solid var(--yellow); color:#1a1a1a}
    .btn-outline:hover{background:var(--yellow)}

    /* Header */
    .site-header{position:sticky; top:0; z-index:20; background:rgba(255,255,255,.9); backdrop-filter:saturate(180%) blur(10px); border-bottom:1px solid #eee}
    .nav{display:flex; align-items:center; justify-content:space-between; gap:1rem; height:64px}
    .brand{display:flex; align-items:center; gap:.75rem; font-weight:900}
    .logo{width:36px; height:36px; border-radius:50%; background:var(--yellow); display:grid; place-items:center; box-shadow:0 2px 10px rgba(0,0,0,.06)}
    .logo svg{width:22px; height:22px}
    .nav-links{display:flex; gap:1.25rem; align-items:center}
    .nav-links a{font-weight:700}

    /* Hero */
    .hero{isolation:isolate; position:relative; overflow:hidden; background:linear-gradient(180deg,#fff 0%, #fff 55%, var(--sky) 55%, var(--sky) 100%)}
    .hero-grid{display:grid; grid-template-columns:1.1fr .9fr; gap:48px; padding:64px 0 40px}
    .eyebrow{display:inline-block; font-weight:900; text-transform:uppercase; letter-spacing:.12em; font-size:.78rem; color:#5b5b5b}
    .hero h1{font-size:clamp(2rem,3vw+1rem,3.25rem); line-height:1.15; margin:.5rem 0 1rem; color:var(--ink)}
    .hero p.lede{font-size:1.125rem; color:#444; max-width:52ch}
    .hero-cta{display:flex; flex-wrap:wrap; gap:.75rem; margin-top:1.25rem}
    .hero-img{border-radius:var(--radius-xl); overflow:hidden; box-shadow:var(--shadow)}
    .badges{display:flex; gap:1rem; align-items:center; margin-top:1.25rem}
    .badge{background:#fff; border:1px solid #eee; border-radius:999px; padding:.5rem .75rem; font-weight:700}

    /* Stats */
    .stats{padding:36px 0}
    .stat-grid{display:grid; grid-template-columns:repeat(4,1fr); gap:16px}
    .stat{background:#fff; border:1px solid #eee; border-radius:var(--radius-lg); padding:18px; text-align:center; box-shadow:var(--shadow)}
    .stat .num{font-size:1.75rem; font-weight:900}
    .stat .label{font-weight:700; color:#5b5b5b}

    /* Story */
    .section{padding:64px 0}
    .section h2{font-size:clamp(1.6rem,1.5vw+1rem,2.2rem); line-height:1.2; color:var(--ink)}
    .two-col{display:grid; grid-template-columns:1fr 1fr; gap:36px; align-items:center}
    .card{background:#fff; border:1px solid #eee; border-radius:var(--radius-xl); padding:28px; box-shadow:var(--shadow)}
    .list{padding-left:1.1rem}
    .list li{margin:.35rem 0}
    .stamp{display:inline-flex; align-items:center; gap:.5rem; background:var(--yellow); padding:.35rem .6rem; border-radius:999px; font-weight:900; margin-top:.75rem}

    /* Impact tiers */
    .tiers{display:grid; grid-template-columns:repeat(3,1fr); gap:24px; margin-top:24px}
    .tier{background:#fff; border:2px solid #eee; border-radius:var(--radius-xl); box-shadow:var(--shadow); padding:28px; transition:transform .2s ease, box-shadow .2s ease, border-color .2s ease}
    .tier:hover{transform:translateY(-4px); box-shadow:var(--shadow-press); border-color:var(--yellow)}
    .price{font-size:2rem; font-weight:900}
    .tier .desc{color:#444}

    /* CTA band */
    .cta-band{position:relative; overflow:hidden;}
    .cta-inner{display:grid; grid-template-columns:1.2fr .8fr; align-items:center; gap:28px; background:var(--yellow); border-radius:var(--radius-xl); padding:32px; box-shadow:var(--shadow)}
    .cta-inner h3{margin:0; font-size:1.75rem}

    /* FAQ */
    details{background:#fff; border:1px solid #eee; border-radius:var(--radius-lg); padding:16px 18px; box-shadow:var(--shadow)}
    details+details{margin-top:12px}
    summary{cursor:pointer; font-weight:900}

    /* Footer */
    .site-footer{background:#0f0f0f; color:#e8e8e8; padding:48px 0}
    .footer-grid{display:grid; grid-template-columns:1.2fr .8fr; gap:28px}
    .site-footer a{color:#e8e8e8}
    .footer-brand{display:flex; align-items:center; gap:.75rem}

    /* Responsive */
    @media (max-width: 960px){
      .hero-grid, .two-col, .cta-inner, .footer-grid{grid-template-columns:1fr}
      .stat-grid{grid-template-columns:repeat(2,1fr)}
      .tiers{grid-template-columns:1fr}
    }
    @media (max-width: 520px){
      .nav{height:auto; padding:10px 0; gap:12px; flex-wrap:wrap}
      .hero-grid{gap:28px; padding:36px 0 24px}
      .stat-grid{grid-template-columns:1fr}
    }

    /* Accessibility focus */
    :focus-visible{outline:3px solid var(--accent); outline-offset:3px}
  </style>
</head>
<body>
  <!-- Header -->
  <header class="site-header">
    <div class="container nav">
      <a class="brand" href="#top" aria-label="charity: water — 返回顶部">
        <span class="logo" aria-hidden="true">
          <!-- Droplet icon -->
          <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
            <path d="M12 3C12 3 6 10 6 14.5C6 18.09 8.91 21 12.5 21C16.09 21 19 18.09 19 14.5C19 10 12 3 12 3Z" stroke="#111" stroke-width="1.8" fill="#fff"/>
          </svg>
        </span>
        <span>charity: water — 校园行动</span>
      </a>
      <nav class="nav-links" aria-label="主导航">
        <a href="#story">故事</a>
        <a href="#impact">影响力</a>
        <a href="#faq">常见问答</a>
        <a class="btn btn-primary" href="#donate">立即行动</a>
      </nav>
    </div>
  </header>

  <!-- Hero -->
  <section class="hero" id="top">
    <div class="container hero-grid">
      <div>
        <span class="eyebrow">大学生一起，改变用水未来</span>
        <h1>一杯咖啡的钱，<br>为偏远社区带去<strong>安全饮用水</strong></h1>
        <p class="lede">全球仍有数亿人缺乏安全饮用水。加入校园行动，用你的声音、时间或小额捐赠，让清洁水源成为每个人的日常。</p>
        <div class="hero-cta">
          <a class="btn btn-primary" href="#donate" aria-label="捐赠或发起筹款">捐赠 / 发起筹款</a>
          <a class="btn btn-outline" href="#story" aria-label="了解项目故事与透明资助原则">了解更多</a>
        </div>
        <div class="badges" aria-label="信任与透明徽章">
          <span class="badge">100% 资金直达项目*</span>
          <span class="badge">可追踪地图与报告</span>
        </div>
      </div>
      <figure class="hero-img">
        <!-- 占位图：请替换为 img/hero.jpg -->
        <img src="img/hero.jpg" alt="学生志愿者在农村社区安装净水设施，孩子们围在旁边微笑" />
      </figure>
    </div>
  </section>

  <!-- Stats -->
  <section class="stats" aria-label="关键数据">
    <div class="container stat-grid">
      <div class="stat">
        <div class="num">785M+</div>
        <div class="label">无安全饮水的人口</div>
      </div>
      <div class="stat">
        <div class="num">$20</div>
        <div class="label">可为一人提供用水*</div>
      </div>
      <div class="stat">
        <div class="num">100%</div>
        <div class="label">公众捐款直达项目</div>
      </div>
      <div class="stat">
        <div class="num">大学生</div>
        <div class="label">最强的改变力量</div>
      </div>
    </div>
  </section>

  <!-- Story -->
  <section id="story" class="section">
    <div class="container two-col">
      <figure class="card">
        <!-- 占位图：请替换为 img/story.jpg -->
        <img src="img/story.jpg" alt="一位社区母亲拧开新安装的取水点，干净的水从水龙头流出" />
        <figcaption class="stamp">真实故事 · 可验证影响</figcaption>
      </figure>
      <div>
        <h2>水，改变一切</h2>
        <p>有了安全用水，孩子能按时上学，家庭减少疾病负担，社区可以发展小生意。通过与当地伙伴合作，项目包括打井、雨水收集、过滤系统与卫生教育，确保长期可持续。</p>
        <ul class="list">
          <li><strong>本地化实施：</strong>与社区共创，建立维护与培训机制。</li>
          <li><strong>透明追踪：</strong>项目坐标、照片与报告全部公开。</li>
          <li><strong>长期影响：</strong>改善健康、教育与经济机会。</li>
        </ul>
        <div class="hero-cta" style="margin-top:1rem">
          <a class="btn btn-primary" href="#impact">查看影响力</a>
          <a class="btn btn-outline" href="#donate">加入我们</a>
        </div>
      </div>
    </div>
  </section>

  <!-- Impact / Donation tiers -->
  <section id="impact" class="section" aria-labelledby="impact-title">
    <div class="container">
      <h2 id="impact-title">你的支持 = 立刻产生的影响</h2>
      <p>以下为示意级别；实际成本因国家与方案不同而异。你也可以选择任意金额支持或发起生日筹款。</p>
      <div class="tiers" id="donate">
        <article class="tier" aria-label="支持 20 美元">
          <h3 class="price">$20</h3>
          <p class="desc">为 1 人提供长期安全饮用水*</p>
          <a class="btn btn-primary" href="#" aria-label="捐赠20美元（示例按钮，部署后替换链接）">捐出 $20</a>
        </article>
        <article class="tier" aria-label="支持 60 美元">
          <h3 class="price">$60</h3>
          <p class="desc">为 3 人提供用水与卫生教育</p>
          <a class="btn btn-primary" href="#" aria-label="捐赠60美元（示例按钮，部署后替换链接）">捐出 $60</a>
        </article>
        <article class="tier" aria-label="支持 300 美元">
          <h3 class="price">$300</h3>
          <p class="desc">支持一个家庭的取水点与维护</p>
          <a class="btn btn-primary" href="#" aria-label="捐赠300美元（示例按钮，部署后替换链接）">捐出 $300</a>
        </article>
      </div>

      <div class="card" style="margin-top:24px">
        <strong>* 说明：</strong>成本为常见传播口径的估算值，仅用于课堂演示。请在正式发布前核对并替换为权威来源与最新数字；若与 charity: water 官方表述不一致，以官方为准。
      </div>
    </div>
  </section>

  <!-- CTA band -->
  <section class="section cta-band" aria-label="行动号召">
    <div class="container">
      <div class="cta-inner">
        <div>
          <h3>3 分钟加入：发起你的校园筹款</h3>
          <p>选择生日捐、社团挑战或毕业纪念活动。我们提供模板帖文、二维码海报与进度追踪表，帮你把善意变成看得见的改变。</p>
          <div class="hero-cta">
            <a class="btn btn-outline" href="#" aria-label="下载校园行动工具包（示例链接）">下载行动工具包</a>
            <a class="btn btn-primary" href="#donate" aria-label="立即开始捐赠或筹款">现在就开始</a>
          </div>
        </div>
        <figure class="hero-img" style="margin:0">
          <!-- 占位图：请替换为 img/toolkit.jpg -->
          <img src="img/toolkit.jpg" alt="校园行动工具包示意图：海报、二维码和社交媒体模板" />
        </figure>
      </div>
    </div>
  </section>

  <!-- FAQ -->
  <section id="faq" class="section" aria-labelledby="faq-title">
    <div class="container">
      <h2 id="faq-title">常见问答</h2>
      <details>
        <summary>如何确保捐款被妥善使用？</summary>
        <p>课堂演示版本强调「透明追踪」与「100%直达项目」理念。部署前请链接至官方披露页、审计报告与项目地图。</p>
      </details>
      <details>
        <summary>我可以用哪些方式参与？</summary>
        <p>捐款、发起个人/团队筹款、成为校园大使、志愿宣传（分享故事、组织活动）。</p>
      </details>
      <details>
        <summary>页面里的图片与数据可以直接用吗？</summary>
        <p>当前为占位内容，用于课堂作业。请替换为你有权使用的图片与最新权威数据。</p>
      </details>
    </div>
  </section>

  <!-- Footer -->
  <footer class="site-footer" role="contentinfo">
    <div class="container footer-grid">
      <div>
        <div class="footer-brand">
          <span class="logo" aria-hidden="true">
            <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
              <path d="M12 3C12 3 6 10 6 14.5C6 18.09 8.91 21 12.5 21C16.09 21 19 18.09 19 14.5C19 10 12 3 12 3Z" stroke="#111" stroke-width="1.8" fill="#fff"/>
            </svg>
          </span>
          <strong>charity: water — 校园行动</strong>
        </div>
        <p style="margin-top:.5rem; color:#bdbdbd">本页面为学习项目示例。品牌名称仅用于课堂练习，发布前请遵循品牌与版权指南。</p>
      </div>
      <div>
        <p><strong>联系与社媒</strong></p>
        <p><a href="#">Instagram</a> · <a href="#">TikTok</a> · <a href="#">微博</a></p>
        <p><a href="#top" aria-label="返回顶部">返回顶部 ↑</a></p>
      </div>
    </div>
  </footer>
</body>
</html>
