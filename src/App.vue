<script setup>
const navItems = [
  { href: '#traits', label: '性格' },
  { href: '#price', label: '价格' },
  { href: '#care', label: '养护' },
  { href: '#daily', label: '日常' },
]

const traits = [
  {
    title: '亲人但不黏腻',
    text: '喜欢跟着人走来走去，像一个安静的小影子，也能自己找窗口晒太阳。',
  },
  {
    title: '体型成长周期长',
    text: '完全成熟可能需要 3-5 年，幼猫时期要重视营养、关节和体重管理。',
  },
  {
    title: '毛量需要维护',
    text: '每周梳毛 2-4 次，换毛季增加频率，减少打结和吞毛问题。',
  },
]

const priceCards = [
  {
    level: '宠物级幼猫',
    price: '$900-$2,200',
    points: [
      '适合作为家庭伴侣，不以繁育或参赛为目标。',
      '重点看健康记录、父母体检和繁育舍环境。',
      '建议确认是否包含疫苗、驱虫、芯片或绝育条款。',
    ],
  },
  {
    level: '品相优良 / 血统清晰',
    price: 'JPY ¥330,000-¥780,000',
    points: [
      '通常有更完整的血统资料和父母健康筛查。',
      '毛色、骨量、耳位、尾长等会影响价格。',
      '签约前看清退换、遗传病保障和运输责任。',
    ],
  },
  {
    level: '月度养护预算',
    price: '¥500-¥1,500+',
    points: [
      '包括主粮、罐头、猫砂、梳毛工具和基础清洁。',
      '大型猫用品要选更稳的猫爬架、航空箱和猫砂盆。',
      '体检、疫苗、绝育、保险或突发医疗需另留预算。',
    ],
  },
]

const careItems = [
  {
    title: '营养',
    text: '选择适合幼猫的高蛋白主粮，按体况调整喂食量，避免只追求“快速长大”。',
  },
  {
    title: '运动',
    text: '准备结实猫爬架、长逗猫棒和可奔跑的路线，让大爪爪有地方释放精力。',
  },
  {
    title: '健康',
    text: '购买前询问 HCM、髋关节、PKDef 等健康筛查，回家后按兽医建议体检。',
  },
]

const photos = [
  {
    src: 'https://upload.wikimedia.org/wikipedia/commons/8/8c/Maine_Coon_kitten.jpg',
    fallbackSrc: 'https://upload.wikimedia.org/wikipedia/commons/8/8c/Maine_Coon_kitten.jpg',
    alt: '灰色缅因猫幼猫趴在床上',
    caption: '灰色幼猫，能看到蓬松耳毛和大爪子。',
    sourceName: 'Wikimedia Commons',
    source: 'https://commons.wikimedia.org/wiki/File:Maine_Coon_kitten.jpg',
  },
  {
    src: 'https://upload.wikimedia.org/wikipedia/commons/6/6d/Maine_Coon_Kitten.jpg',
    fallbackSrc: 'https://upload.wikimedia.org/wikipedia/commons/8/8c/Maine_Coon_kitten.jpg',
    alt: '棕虎斑缅因猫幼猫趴在地毯上',
    caption: '棕虎斑幼猫，脸型和前爪很有代表性。',
    sourceName: 'Wikimedia Commons',
    source: 'https://commons.wikimedia.org/wiki/File:Maine_Coon_Kitten.jpg',
  },
  {
    src: '/assets/maine-coon-adult-grass.jpg',
    fallbackSrc: '/assets/maine-coon-adult-grass.jpg',
    alt: '草地里正脸看镜头的成年缅因猫',
    caption: '成年缅因猫正脸照，耳尖毛和蓬松围脖很明显。',
    sourceName: 'Unsplash',
    source: 'https://unsplash.com/photos/a-long-haired-cat-sitting-in-the-grass-SX_lq2EvzPo',
  },
]

const dailyTips = [
  '每天安排 15-30 分钟互动游戏，幼猫会更自信。',
  '从小练习梳毛、剪指甲和进航空箱，以后看医生会轻松很多。',
  '如果家里已有宠物，先隔离适应气味，再逐步见面。',
  '不要只被“巨型猫”吸引，它真正可爱的地方是稳定、亲切和慢热的陪伴感。',
]

function useFallbackPhoto(event, fallbackSrc) {
  if (!fallbackSrc || event.target.dataset.fallbackApplied) return
  event.target.dataset.fallbackApplied = 'true'
  event.target.src = fallbackSrc
}
</script>

<template>
  <nav class="nav" aria-label="主导航">
    <div class="brand"><span class="brand-mark">M</span>小缅因猫手册</div>
    <div class="nav-links">
      <a v-for="item in navItems" :key="item.href" :href="item.href">{{ item.label }}</a>
    </div>
  </nav>

  <header class="hero">
    <div class="hero-copy">
      <p class="eyebrow">Maine Coon Kitten</p>
      <h1>小缅因猫</h1>
      <p>耳尖带小毛簇，爪子像雪地小靴子，性格却像温柔的家庭成员。这里是一份可爱但实用的缅因猫幼猫介绍。</p>
      <div class="actions">
        <a class="button primary" href="#price">查看价格预算</a>
        <a class="button" href="#care">了解养护重点</a>
      </div>
    </div>
  </header>

  <main>
    <section id="traits" class="traits">
      <div class="section-head">
        <h2>大体型，小奶音，慢慢长成威风的朋友。</h2>
        <p>缅因猫是大型长毛猫，幼猫时期已经能看出宽鼻梁、蓬松尾巴和耳尖毛。它们通常亲人、好奇、爱参与家庭活动，但成熟较慢，需要耐心陪伴。</p>
      </div>
      <div class="trait-grid">
        <article v-for="trait in traits" :key="trait.title" class="trait">
          <b>{{ trait.title }}</b>
          <p>{{ trait.text }}</p>
        </article>
      </div>
    </section>

    <section id="price" class="prices">
      <div class="section-head">
        <h2>价格不是只有买猫那一刻。</h2>
        <p>以下是常见预算区间，实际会因城市、血统证书、繁育环境、疫苗驱虫、绝育协议和售后保障而变化。</p>
      </div>
      <div class="price-grid">
        <article v-for="card in priceCards" :key="card.level" class="price-card">
          <div class="price-top">
            <span>{{ card.level }}</span>
            <div class="price">{{ card.price }}</div>
          </div>
          <div class="price-body">
            <ul>
              <li v-for="point in card.points" :key="point">{{ point }}</li>
            </ul>
          </div>
        </article>
      </div>
      <div class="budget-strip">
        <strong>建议首年准备：</strong>购猫费用之外，额外预留 ¥3,000-¥8,000 用于体检、疫苗、绝育、用品升级和应急医疗。
      </div>
    </section>

    <section id="care" class="care">
      <div class="section-head">
        <h2>养护重点：吃得稳，梳得勤，空间够。</h2>
        <p>缅因猫幼猫看起来软乎乎，但骨架和活动量都不小。把基础条件准备好，它会更从容地长成漂亮的大猫。</p>
      </div>
      <div class="care-grid">
        <article v-for="item in careItems" :key="item.title" class="care-item">
          <b>{{ item.title }}</b>
          <p>{{ item.text }}</p>
        </article>
      </div>
    </section>

    <section id="daily">
      <div class="section-head">
        <h2>几张真实的缅因猫照片。</h2>
        <p>插画负责可爱气氛，真实照片负责让你看清缅因猫幼猫的耳簇、大爪子、长毛和成年后更威风的轮廓。</p>
      </div>
      <div class="photo-gallery">
        <figure v-for="photo in photos" :key="photo.src" class="photo-card">
          <img :src="photo.src" :alt="photo.alt" @error="useFallbackPhoto($event, photo.fallbackSrc)">
          <figcaption>
            {{ photo.caption }}来源：
            <a :href="photo.source" target="_blank" rel="noreferrer">{{ photo.sourceName }}</a>
          </figcaption>
        </figure>
      </div>
      <div class="gallery">
        <img src="/assets/maine-coon-kitten.svg" alt="坐在窗边的小缅因猫插画">
        <div>
          <h2>适合它的家，会有一点点宽敞，也有很多耐心。</h2>
          <ul class="mini-list">
            <li v-for="tip in dailyTips" :key="tip">{{ tip }}</li>
          </ul>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div>价格区间仅作购买前预算参考；实际交易请优先选择正规繁育者或领养渠道，并核验健康资料与合同。</div>
  </footer>
</template>

<style>
:root {
  --ink: #26302c;
  --muted: #66716b;
  --paper: #fffaf1;
  --cream: #f7ead6;
  --green: #456f5c;
  --leaf: #9fbd8f;
  --coral: #e9695b;
  --gold: #f2bd49;
  --blue: #8fc5df;
  --line: rgba(38, 48, 44, .16);
  --shadow: 0 24px 70px rgba(46, 38, 31, .16);
}

* { box-sizing: border-box; }

html { scroll-behavior: smooth; }

body {
  margin: 0;
  color: var(--ink);
  font-family: "Microsoft YaHei", "PingFang SC", system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
  line-height: 1.6;
  background: var(--paper);
}

img { max-width: 100%; display: block; }

a { color: inherit; }

.nav {
  position: fixed;
  z-index: 10;
  top: 0;
  left: 0;
  right: 0;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 18px clamp(18px, 4vw, 56px);
  background: rgba(255, 250, 241, .8);
  border-bottom: 1px solid rgba(38, 48, 44, .08);
  backdrop-filter: blur(14px);
}

.brand {
  display: flex;
  align-items: center;
  gap: 10px;
  font-weight: 800;
  letter-spacing: 0;
}

.brand-mark {
  display: grid;
  width: 34px;
  height: 34px;
  place-items: center;
  border-radius: 50%;
  color: white;
  background: var(--green);
  font-size: 18px;
}

.nav-links {
  display: flex;
  gap: clamp(14px, 2vw, 26px);
  color: #425048;
  font-size: 14px;
  font-weight: 700;
}

.nav-links a {
  text-decoration: none;
  border-bottom: 2px solid transparent;
}

.nav-links a:hover { border-color: var(--coral); }

.hero {
  min-height: 88vh;
  display: grid;
  align-items: end;
  padding: 112px clamp(20px, 5vw, 72px) 52px;
  background:
    linear-gradient(90deg, rgba(255, 250, 241, .96) 0%, rgba(255, 250, 241, .74) 43%, rgba(255, 250, 241, .08) 72%),
    url("/assets/maine-coon-kitten.svg") center / cover no-repeat;
}

.hero-copy {
  width: min(650px, 100%);
  padding-bottom: clamp(10px, 5vh, 52px);
}

.eyebrow {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  margin: 0 0 14px;
  color: var(--green);
  font-weight: 800;
  font-size: 14px;
}

.eyebrow::before {
  content: "";
  width: 34px;
  height: 4px;
  border-radius: 999px;
  background: var(--coral);
}

h1 {
  margin: 0;
  max-width: 11ch;
  font-size: clamp(48px, 8vw, 104px);
  line-height: .98;
  letter-spacing: 0;
}

.hero p {
  max-width: 570px;
  margin: 24px 0 30px;
  color: #4d5a52;
  font-size: clamp(17px, 2vw, 21px);
}

.actions {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
}

.button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-height: 46px;
  padding: 12px 18px;
  border: 1px solid var(--green);
  border-radius: 999px;
  text-decoration: none;
  font-weight: 800;
}

.button.primary {
  color: #fff;
  background: var(--green);
  box-shadow: 0 12px 30px rgba(69, 111, 92, .24);
}

main section {
  padding: clamp(58px, 8vw, 96px) clamp(20px, 5vw, 72px);
}

.section-head {
  display: grid;
  grid-template-columns: minmax(0, 1fr) minmax(240px, 460px);
  gap: 28px;
  align-items: end;
  max-width: 1180px;
  margin: 0 auto 34px;
}

h2 {
  margin: 0;
  font-size: clamp(30px, 4vw, 50px);
  line-height: 1.12;
  letter-spacing: 0;
}

.section-head p,
.note {
  margin: 0;
  color: var(--muted);
}

.traits { background: #eef6ef; }

.trait-grid,
.price-grid,
.care-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 18px;
  max-width: 1180px;
  margin: 0 auto;
}

.trait,
.price-card,
.care-item {
  border: 1px solid var(--line);
  border-radius: 8px;
  background: rgba(255, 255, 255, .72);
  box-shadow: 0 10px 30px rgba(54, 73, 61, .08);
}

.trait,
.care-item { padding: 24px; }

.trait b,
.care-item b {
  display: block;
  margin-bottom: 8px;
  font-size: 20px;
}

.trait p,
.care-item p {
  margin: 0;
  color: var(--muted);
}

.prices { background: linear-gradient(180deg, #fffaf1 0%, #f9f1df 100%); }

.price-card { overflow: hidden; }

.price-top {
  padding: 22px 22px 18px;
  color: #fff;
  background: var(--green);
}

.price-card:nth-child(2) .price-top { background: var(--coral); }
.price-card:nth-child(3) .price-top { background: #3d7193; }

.price-top span {
  display: block;
  margin-bottom: 8px;
  font-size: 14px;
  font-weight: 800;
  opacity: .88;
}

.price {
  font-size: clamp(29px, 3.2vw, 42px);
  font-weight: 900;
  line-height: 1.05;
}

.price-body {
  padding: 20px 22px 24px;
  background: rgba(255, 255, 255, .8);
}

.price-body ul {
  padding: 0;
  margin: 0;
  list-style: none;
}

.price-body li {
  position: relative;
  padding-left: 22px;
  margin: 12px 0;
  color: #536056;
}

.price-body li::before {
  content: "";
  position: absolute;
  left: 0;
  top: .68em;
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: var(--gold);
}

.care { background: #f7fbff; }

.budget-strip {
  max-width: 1180px;
  margin: 22px auto 0;
  padding: 22px;
  border-left: 7px solid var(--coral);
  border-radius: 8px;
  background: #fff;
  box-shadow: var(--shadow);
}

.budget-strip strong {
  color: var(--green);
  font-size: 20px;
}

.gallery {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 22px;
  max-width: 1180px;
  margin: 0 auto;
  align-items: center;
}

.gallery img {
  width: 100%;
  border-radius: 8px;
  box-shadow: var(--shadow);
  background: var(--cream);
}

.photo-gallery {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 18px;
  max-width: 1180px;
  margin: 0 auto 34px;
}

.photo-card {
  margin: 0;
  overflow: hidden;
  border: 1px solid var(--line);
  border-radius: 8px;
  background: #fff;
  box-shadow: 0 14px 34px rgba(54, 73, 61, .12);
}

.photo-card img {
  width: 100%;
  aspect-ratio: 4 / 3;
  object-fit: contain;
  background: #edf4f7;
}

.photo-card figcaption {
  padding: 14px 16px 16px;
  color: #4c5b52;
  font-size: 14px;
}

.photo-card a {
  color: var(--green);
  font-weight: 800;
  text-decoration-thickness: 2px;
  text-underline-offset: 3px;
}

.mini-list {
  display: grid;
  gap: 14px;
  margin: 0;
  padding: 0;
  list-style: none;
}

.mini-list li {
  padding: 16px 18px;
  border-left: 6px solid var(--leaf);
  border-radius: 8px;
  background: #fff;
  color: #4c5b52;
}

footer {
  padding: 28px clamp(20px, 5vw, 72px);
  color: #59665f;
  background: #e7efe8;
  font-size: 14px;
}

footer div {
  max-width: 1180px;
  margin: 0 auto;
}

@media (max-width: 860px) {
  .nav {
    position: sticky;
    flex-direction: column;
    align-items: flex-start;
    gap: 12px;
  }

  .nav-links {
    width: 100%;
    overflow-x: auto;
    padding-bottom: 2px;
  }

  .hero {
    min-height: 82vh;
    background:
      linear-gradient(180deg, rgba(255, 250, 241, .98) 0%, rgba(255, 250, 241, .82) 45%, rgba(255, 250, 241, .24) 100%),
      url("/assets/maine-coon-kitten.svg") center bottom / cover no-repeat;
  }

  .section-head,
  .gallery {
    grid-template-columns: 1fr;
  }

  .trait-grid,
  .price-grid,
  .care-grid,
  .photo-gallery {
    grid-template-columns: 1fr;
  }
}
</style>
