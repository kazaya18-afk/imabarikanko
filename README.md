<!DOCTYPE html>

<html lang="ja">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>しいちゃんの今治観光</title>
<link href="https://fonts.googleapis.com/css2?family=Noto+Serif+JP:wght@300;400;700&family=Shippori+Mincho:wght@400;700&family=Bebas+Neue&display=swap" rel="stylesheet">
<style>
 :root {
   --ink: #1a1008;
   --cream: #f5efe3;
   --orange: #e05c1a;
   --gold: #c9933a;
   --sea: #2a6580;
   --sea-light: #4a8fa8;
   --mist: #d6cbb8;
 }

- { margin: 0; padding: 0; box-sizing: border-box; }

html { scroll-behavior: smooth; }

body {
background: var(–cream);
color: var(–ink);
font-family: ‘Noto Serif JP’, serif;
overflow-x: hidden;
}

/* ===== HERO ===== */
.hero {
position: relative;
height: 100vh;
display: flex;
align-items: center;
justify-content: center;
overflow: hidden;
background: var(–ink);
}

.hero-bg {
position: absolute;
inset: 0;
background:
radial-gradient(ellipse at 20% 60%, rgba(42,101,128,0.5) 0%, transparent 60%),
radial-gradient(ellipse at 80% 40%, rgba(201,147,58,0.3) 0%, transparent 50%),
linear-gradient(160deg, #0d1b24 0%, #1a1008 60%, #2a1a05 100%);
}

/* Wave SVG decoration */
.hero-waves {
position: absolute;
bottom: 0;
left: 0;
width: 100%;
height: 140px;
opacity: 0.18;
}

.hero-content {
position: relative;
z-index: 2;
text-align: center;
padding: 2rem;
}

.hero-sub {
font-family: ‘Bebas Neue’, sans-serif;
font-size: clamp(0.9rem, 2vw, 1.1rem);
letter-spacing: 0.5em;
color: var(–gold);
margin-bottom: 1rem;
opacity: 0;
animation: fadeUp 0.8s 0.3s forwards;
}

.hero-title {
font-family: ‘Shippori Mincho’, serif;
font-size: clamp(3rem, 9vw, 7rem);
font-weight: 700;
color: var(–cream);
line-height: 1.1;
opacity: 0;
animation: fadeUp 0.8s 0.6s forwards;
text-shadow: 0 4px 40px rgba(201,147,58,0.3);
}

.hero-title span { color: var(–orange); }

.hero-desc {
font-size: clamp(0.9rem, 2vw, 1.05rem);
color: var(–mist);
margin-top: 1.5rem;
letter-spacing: 0.08em;
line-height: 2;
opacity: 0;
animation: fadeUp 0.8s 0.9s forwards;
}

.scroll-hint {
position: absolute;
bottom: 2rem;
left: 50%;
transform: translateX(-50%);
color: var(–gold);
font-family: ‘Bebas Neue’, sans-serif;
letter-spacing: 0.3em;
font-size: 0.75rem;
opacity: 0;
animation: fadeUp 0.8s 1.3s forwards;
display: flex;
flex-direction: column;
align-items: center;
gap: 0.5rem;
}

.scroll-hint::after {
content: ‘’;
width: 1px;
height: 50px;
background: linear-gradient(to bottom, var(–gold), transparent);
animation: scrollLine 1.5s infinite;
}

/* ===== NAV ===== */
nav {
position: fixed;
top: 0;
width: 100%;
z-index: 100;
padding: 1rem 2rem;
display: flex;
justify-content: space-between;
align-items: center;
background: rgba(26,16,8,0.85);
backdrop-filter: blur(10px);
border-bottom: 1px solid rgba(201,147,58,0.2);
}

.nav-logo {
font-family: ‘Shippori Mincho’, serif;
color: var(–gold);
font-size: 1.1rem;
font-weight: 700;
letter-spacing: 0.1em;
}

.nav-links {
display: flex;
gap: 2rem;
list-style: none;
}

.nav-links a {
font-family: ‘Noto Serif JP’, serif;
color: var(–mist);
text-decoration: none;
font-size: 0.85rem;
letter-spacing: 0.1em;
transition: color 0.3s;
}

.nav-links a:hover { color: var(–gold); }

/* ===== SECTION BASE ===== */
section {
padding: 6rem 2rem;
max-width: 1200px;
margin: 0 auto;
}

.section-label {
font-family: ‘Bebas Neue’, sans-serif;
letter-spacing: 0.5em;
color: var(–orange);
font-size: 0.8rem;
margin-bottom: 0.5rem;
}

.section-title {
font-family: ‘Shippori Mincho’, serif;
font-size: clamp(2rem, 4vw, 3rem);
font-weight: 700;
color: var(–ink);
margin-bottom: 1rem;
line-height: 1.3;
}

.section-title span { color: var(–sea); }

.section-intro {
color: #5a4a35;
line-height: 2;
font-size: 0.95rem;
max-width: 600px;
margin-bottom: 3rem;
}

.divider {
width: 60px;
height: 3px;
background: var(–gold);
margin: 1.5rem 0;
}

/* ===== SIGHTS GRID ===== */
.sights-grid {
display: grid;
grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
gap: 2rem;
}

.sight-card {
background: white;
border-radius: 2px;
overflow: hidden;
box-shadow: 0 4px 30px rgba(26,16,8,0.08);
transition: transform 0.4s, box-shadow 0.4s;
cursor: default;
}

.sight-card:hover {
transform: translateY(-6px);
box-shadow: 0 16px 50px rgba(26,16,8,0.18);
}

.sight-card-img {
width: 100%;
height: 200px;
display: flex;
align-items: center;
justify-content: center;
font-size: 5rem;
position: relative;
overflow: hidden;
}

.sight-card-body {
padding: 1.5rem;
}

.sight-card-tag {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 0.7rem;
letter-spacing: 0.3em;
color: var(–sea);
margin-bottom: 0.4rem;
}

.sight-card-name {
font-family: ‘Shippori Mincho’, serif;
font-size: 1.3rem;
font-weight: 700;
margin-bottom: 0.7rem;
color: var(–ink);
}

.sight-card-desc {
font-size: 0.85rem;
line-height: 1.9;
color: #5a4a35;
}

/* ===== FOOD SECTION ===== */
.food-section-bg {
background: var(–ink);
color: var(–cream);
padding: 6rem 0;
margin: 0;
max-width: none;
}

.food-inner {
max-width: 1200px;
margin: 0 auto;
padding: 0 2rem;
}

.food-section-bg .section-title { color: var(–cream); }
.food-section-bg .section-intro { color: var(–mist); }

.food-grid {
display: grid;
grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
gap: 1.5rem;
margin-top: 2rem;
}

.food-card {
border: 1px solid rgba(201,147,58,0.25);
border-radius: 2px;
padding: 2rem 1.5rem;
transition: border-color 0.3s, background 0.3s;
position: relative;
overflow: hidden;
}

.food-card::before {
content: ‘’;
position: absolute;
top: 0; left: 0;
width: 4px; height: 100%;
background: var(–gold);
transform: scaleY(0);
transform-origin: bottom;
transition: transform 0.4s;
}

.food-card:hover::before { transform: scaleY(1); }
.food-card:hover {
border-color: var(–gold);
background: rgba(201,147,58,0.07);
}

.food-emoji { font-size: 2.5rem; margin-bottom: 1rem; }

.food-name {
font-family: ‘Shippori Mincho’, serif;
font-size: 1.25rem;
font-weight: 700;
color: var(–gold);
margin-bottom: 0.5rem;
}

.food-desc {
font-size: 0.85rem;
line-height: 2;
color: var(–mist);
}

/* ===== SEASON SECTION ===== */
.season-grid {
display: grid;
grid-template-columns: repeat(2, 1fr);
gap: 1.5rem;
}

@media (max-width: 600px) {
.season-grid { grid-template-columns: 1fr; }
}

.season-card {
padding: 2rem;
border-left: 4px solid;
background: white;
box-shadow: 0 2px 20px rgba(26,16,8,0.06);
}

.season-card:nth-child(1) { border-color: #7aba78; }
.season-card:nth-child(2) { border-color: #e05c1a; }
.season-card:nth-child(3) { border-color: #c9933a; }
.season-card:nth-child(4) { border-color: #2a6580; }

.season-name {
font-family: ‘Shippori Mincho’, serif;
font-size: 1.2rem;
font-weight: 700;
margin-bottom: 0.7rem;
color: var(–ink);
}

.season-desc {
font-size: 0.85rem;
line-height: 2;
color: #5a4a35;
}

/* ===== ACCESS ===== */
.access-box {
background: white;
border-radius: 2px;
box-shadow: 0 4px 30px rgba(26,16,8,0.08);
padding: 3rem;
display: grid;
grid-template-columns: 1fr 1fr;
gap: 3rem;
align-items: start;
}

@media (max-width: 700px) {
.access-box { grid-template-columns: 1fr; gap: 2rem; }
}

.access-title {
font-family: ‘Shippori Mincho’, serif;
font-size: 1.1rem;
font-weight: 700;
margin-bottom: 1rem;
color: var(–sea);
}

.access-list { list-style: none; }
.access-list li {
font-size: 0.9rem;
line-height: 2;
color: #5a4a35;
padding: 0.4rem 0;
border-bottom: 1px solid #e8e0d0;
display: flex;
gap: 0.7rem;
}

.access-list li span { color: var(–gold); font-weight: 700; }

/* ===== FOOTER ===== */
footer {
background: var(–ink);
color: var(–mist);
text-align: center;
padding: 3rem 2rem;
font-size: 0.85rem;
letter-spacing: 0.1em;
line-height: 2;
}

footer .footer-logo {
font-family: ‘Shippori Mincho’, serif;
font-size: 1.5rem;
color: var(–gold);
margin-bottom: 0.5rem;
}

/* ===== ANIMATIONS ===== */
@keyframes fadeUp {
from { opacity: 0; transform: translateY(30px); }
to { opacity: 1; transform: translateY(0); }
}

@keyframes scrollLine {
0% { transform: scaleY(0); transform-origin: top; }
50% { transform: scaleY(1); transform-origin: top; }
51% { transform: scaleY(1); transform-origin: bottom; }
100% { transform: scaleY(0); transform-origin: bottom; }
}

.fade-in {
opacity: 0;
transform: translateY(30px);
transition: opacity 0.7s, transform 0.7s;
}

.fade-in.visible {
opacity: 1;
transform: none;
}

/* card image backgrounds */
.bg-castle { background: linear-gradient(135deg, #2a6580 0%, #1a4055 100%); }
.bg-bridge { background: linear-gradient(135deg, #c9933a 0%, #8a5a1a 100%); }
.bg-towel  { background: linear-gradient(135deg, #e05c1a 0%, #a03010 100%); }
.bg-sea    { background: linear-gradient(135deg, #4a8fa8 0%, #2a6580 100%); }
.bg-park   { background: linear-gradient(135deg, #7aba78 0%, #3d7a3a 100%); }
.bg-shrine { background: linear-gradient(135deg, #8a2020 0%, #5a1010 100%); }

@media (max-width: 768px) {
.nav-links { display: none; }
.sights-grid { grid-template-columns: 1fr; }
}
</style>

</head>
<body>

<!-- NAV -->

<nav>
 <div class="nav-logo">しいちゃんの今治観光</div>
 <ul class="nav-links">
   <li><a href="#sights">観光地</a></li>
   <li><a href="#food">グルメ</a></li>
   <li><a href="#season">季節情報</a></li>
   <li><a href="#access">アクセス</a></li>
 </ul>
</nav>

<!-- HERO -->

<div class="hero">
 <div class="hero-bg"></div>
 <svg class="hero-waves" viewBox="0 0 1440 140" preserveAspectRatio="none">
   <path d="M0,70 C360,140 720,0 1080,70 C1260,105 1380,50 1440,70 L1440,140 L0,140 Z" fill="#f5efe3"/>
   <path d="M0,100 C400,40 800,120 1200,80 C1320,65 1400,90 1440,100 L1440,140 L0,140 Z" fill="#f5efe3" opacity="0.6"/>
 </svg>
 <div class="hero-content">
   <p class="hero-sub">しいちゃんの今治観光</p>
   <h1 class="hero-title">今<span>治</span><br>観光案内</h1>
   <p class="hero-desc">
     瀬戸内海に抱かれた城下町。<br>
     しまなみ海道の玄関口へ、ようこそ。
   </p>
 </div>
 <div class="scroll-hint">SCROLL</div>
</div>

<!-- SIGHTS -->

<section id="sights">
 <div class="fade-in">
   <p class="section-label">SIGHTSEEING · 観光スポット</p>
   <h2 class="section-title">今治の<span>絶景</span>と名所</h2>
   <div class="divider"></div>
   <p class="section-intro">海と橋と歴史が交わる今治市。瀬戸内の美しい風景の中に、歴史ある城や名橋が佇みます。</p>
 </div>
 <div class="sights-grid">
   <div class="sight-card fade-in">
     <div class="sight-card-img bg-castle">🏯</div>
     <div class="sight-card-body">
       <p class="sight-card-tag">CASTLE · 城</p>
       <h3 class="sight-card-name">今治城</h3>
       <p class="sight-card-desc">藤堂高虎が築いた日本三大水城のひとつ。海水を堀に引き入れた独特の縄張りは必見。天守閣からは瀬戸内海を一望できます。桜の季節は特に美しく、花見スポットとしても人気です。</p>
     </div>
   </div>
   <div class="sight-card fade-in">
     <div class="sight-card-img bg-bridge">🌉</div>
     <div class="sight-card-body">
       <p class="sight-card-tag">BRIDGE · 橋</p>
       <h3 class="sight-card-name">来島海峡大橋</h3>
       <p class="sight-card-desc">しまなみ海道のシンボル、世界初の三連吊橋。全長4105mにも及ぶ橋は、展望台・サンライズ糸山から全景を眺めることができます。朝日や夕暮れ時の景色は圧巻です。</p>
     </div>
   </div>
   <div class="sight-card fade-in">
     <div class="sight-card-img bg-towel">🧣</div>
     <div class="sight-card-body">
       <p class="sight-card-tag">MUSEUM · 博物館</p>
       <h3 class="sight-card-name">タオル美術館</h3>
       <p class="sight-card-desc">今治タオルの歴史と文化を体感できるミュージアム。色とりどりのタオルアートや体験コーナーが充実。ここでしか買えないオリジナル商品も揃います。</p>
     </div>
   </div>
   <div class="sight-card fade-in">
     <div class="sight-card-img bg-sea">⛵</div>
     <div class="sight-card-body">
       <p class="sight-card-tag">ISLAND · 島</p>
       <h3 class="sight-card-name">大島・亀老山展望公園</h3>
       <p class="sight-card-desc">しまなみ海道の最初の島・大島にある絶景スポット。隈研吾設計の展望台から来島海峡大橋と瀬戸内の多島美を眺める360度のパノラマは息をのむ美しさです。</p>
     </div>
   </div>
   <div class="sight-card fade-in">
     <div class="sight-card-img bg-park">🌸</div>
     <div class="sight-card-body">
       <p class="sight-card-tag">PARK · 公園</p>
       <h3 class="sight-card-name">しまなみ海道サイクリング</h3>
       <p class="sight-card-desc">世界が注目するサイクリングルート。今治〜尾道間70kmを自転車で渡る旅は一生の思い出に。レンタサイクルも充実しており、初心者から上級者まで楽しめます。</p>
     </div>
   </div>
   <div class="sight-card fade-in">
     <div class="sight-card-img bg-shrine">⛩️</div>
     <div class="sight-card-body">
       <p class="sight-card-tag">SHRINE · 神社</p>
       <h3 class="sight-card-name">大山祇神社（大三島）</h3>
       <p class="sight-card-desc">全国三千余社の大山祇神社の総本社。国宝・重要文化財の武具コレクションが日本一。境内には樹齢2600年を超える大楠がそびえ、神秘的な空気に満ちています。</p>
     </div>
   </div>
 </div>
</section>

<!-- FOOD -->

<div class="food-section-bg" id="food">
 <div class="food-inner">
   <div class="fade-in">
     <p class="section-label" style="color:var(--orange)">GOURMET · 食べ物</p>
     <h2 class="section-title" style="color:var(--cream)">今治の<span style="color:var(--gold)">名物グルメ</span></h2>
     <div class="divider"></div>
     <p class="section-intro">海の幸と独自の食文化が息づく今治。ここでしか味わえない名物が揃います。</p>
   </div>
   <div class="food-grid">
     <div class="food-card fade-in">
       <div class="food-emoji">🐔</div>
       <p class="food-name">今治焼き鳥</p>
       <p class="food-desc">今治の焼き鳥は串に刺さず、鉄板でプレスして焼くのが特徴。皮・せんざんき（唐揚げ）も名物。市内に100軒以上の焼き鳥店があり「焼き鳥のまち」として知られます。</p>
     </div>
     <div class="food-card fade-in">
       <div class="food-emoji">🐙</div>
       <p class="food-name">せんざんき</p>
       <p class="food-desc">骨付きの鶏肉を揚げた今治発祥の郷土料理。唐揚げの元祖とも言われ、にんにくと生姜が効いた豪快な味わいが魅力。居酒屋や惣菜店で気軽に食べられます。</p>
     </div>
     <div class="food-card fade-in">
       <div class="food-emoji">🐟</div>
       <p class="food-name">鯛めし・海鮮</p>
       <p class="food-desc">瀬戸内の新鮮な海の幸を使った鯛めし。今治スタイルは真鯛の切り身をだし醤油で食べる「宇和島風」と異なり、炊き込みご飯タイプ。新鮮な鯛の刺身もおすすめです。</p>
     </div>
     <div class="food-card fade-in">
       <div class="food-emoji">🍜</div>
       <p class="food-name">今治ラーメン</p>
       <p class="food-desc">鶏ガラや豚骨をベースにした醤油系スープが主流。あっさりとした中にも深いコクがあり、地元民に長く愛されています。老舗から新店まで様々なラーメン店が点在します。</p>
     </div>
     <div class="food-card fade-in">
       <div class="food-emoji">🍊</div>
       <p class="food-name">柑橘スイーツ</p>
       <p class="food-desc">愛媛は全国一の柑橘産地。今治でもみかん・伊予柑・清見・せとかなど種類豊富な柑橘を使ったスイーツが充実。ジェラート・タルト・マーマレードなど土産にも最適です。</p>
     </div>
     <div class="food-card fade-in">
       <div class="food-emoji">🧁</div>
       <p class="food-name">タオルサブレ</p>
       <p class="food-desc">今治タオルをモチーフにしたお菓子など、タオルの街ならではのユニークな土産菓子が揃います。地元の菓子店が作る和洋菓子は、訪れた記念にぴったりです。</p>
     </div>
   </div>
 </div>
</div>

<!-- SEASON -->

<section id="season">
 <div class="fade-in">
   <p class="section-label">SEASON · 季節</p>
   <h2 class="section-title"><span>四季</span>の今治</h2>
   <div class="divider"></div>
   <p class="section-intro">瀬戸内の温暖な気候に恵まれた今治は、一年を通じて楽しめる観光地です。</p>
 </div>
 <div class="season-grid">
   <div class="season-card fade-in">
     <h3 class="season-name">🌸 春（3〜5月）</h3>
     <p class="season-desc">今治城や来島海峡周辺で桜が満開に。しまなみ海道サイクリングのベストシーズンでもあり、穏やかな潮風の中で花見を楽しめます。気温も走りやすく過ごしやすい季節。</p>
   </div>
   <div class="season-card fade-in">
     <h3 class="season-name">☀️ 夏（6〜8月）</h3>
     <p class="season-desc">瀬戸内の青い海と青い空が輝く夏。来島海峡では潮流観察や海水浴も楽しめます。夏祭りや花火大会も各地で開催。早朝サイクリングで涼しく島を巡るのもおすすめです。</p>
   </div>
   <div class="season-card fade-in">
     <h3 class="season-name">🍁 秋（9〜11月）</h3>
     <p class="season-desc">柑橘の収穫期を迎え、みかん狩りが楽しめます。サイクリングにも最適な気候で、紅葉と海の絶景が重なる大三島や亀老山が特に美しい季節。地元グルメも充実します。</p>
   </div>
   <div class="season-card fade-in">
     <h3 class="season-name">❄️ 冬（12〜2月）</h3>
     <p class="season-desc">瀬戸内の温暖な冬は、雪が少なく観光に適しています。冬限定の柑橘（清見・せとか）が旬を迎え、焼き鳥や鍋料理で温まるグルメ旅も格別。空気が澄み橋の眺めも清々しい。</p>
   </div>
 </div>
</section>

<!-- ACCESS -->

<section id="access" style="padding-top:0">
 <div class="fade-in">
   <p class="section-label">ACCESS · アクセス</p>
   <h2 class="section-title">今治への<span>アクセス</span></h2>
   <div class="divider"></div>
 </div>
 <div class="access-box fade-in">
   <div>
     <p class="access-title">🚄 電車でのアクセス</p>
     <ul class="access-list">
       <li><span>松山から</span>JR予讃線 特急いしづちで約35分</li>
       <li><span>高松から</span>JR瀬戸大橋線経由 特急で約90分</li>
       <li><span>岡山から</span>しおかぜで約2時間</li>
     </ul>
     <br>
     <p class="access-title">✈️ 飛行機でのアクセス</p>
     <ul class="access-list">
       <li><span>松山空港から</span>リムジンバス+JR 計約1時間</li>
       <li><span>東京から</span>松山空港まで約80分</li>
       <li><span>大阪から</span>松山空港まで約50分</li>
     </ul>
   </div>
   <div>
     <p class="access-title">🚗 車・バスでのアクセス</p>
     <ul class="access-list">
       <li><span>西瀬戸道（しまなみ）</span>尾道ICから約1時間</li>
       <li><span>松山から</span>国道196号で約50分</li>
       <li><span>高速バス</span>広島・岡山・大阪から直通便あり</li>
     </ul>
     <br>
     <p class="access-title">⛴️ 船でのアクセス</p>
     <ul class="access-list">
       <li><span>広島から</span>スーパージェット約65分</li>
       <li><span>神戸から</span>フェリーで約4〜5時間</li>
       <li><span>大阪から</span>フェリーで約9時間</li>
     </ul>
   </div>
 </div>
</section>

<!-- FOOTER -->

<footer>
 <div class="footer-logo">しいちゃんの今治観光</div>
 <p>IMABARI TOURISM GUIDE</p>
 <p style="margin-top:1rem;font-size:0.75rem;color:#6a5a48">愛媛県今治市 | しまなみ海道の玄関口</p>
</footer>

<script>
 // Scroll fade-in
 const observer = new IntersectionObserver((entries) => {
   entries.forEach((e, i) => {
     if (e.isIntersecting) {
       setTimeout(() => e.target.classList.add('visible'), i * 100);
     }
   });
 }, { threshold: 0.15 });

 document.querySelectorAll('.fade-in').forEach(el => observer.observe(el));
</script>

</body>
</html>