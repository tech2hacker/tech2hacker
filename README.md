

Index · HTML
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>The Local Shop – Fresh Finds, Best Prices</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:wght@500;700;800&family=DM+Sans:wght@400;500;700&display=swap" rel="stylesheet">
<style>
:root{--ink:#1f2a44;--paper:#f7f8fb;--card:#fff;--accent:#f2a900;--accent-d:#c98a00;--muted:#667088;--line:#e3e6ef;--wa:#25d366;--r:16px}
*{box-sizing:border-box;margin:0}
html{scroll-behavior:smooth}
body{font-family:'DM Sans',system-ui,sans-serif;background:var(--paper);color:var(--ink);line-height:1.5}
h1,h2,h3{font-family:'Bricolage Grotesque','DM Sans',sans-serif;line-height:1.1}
button{font:inherit;cursor:pointer}
:focus-visible{outline:3px solid var(--accent);outline-offset:2px}
 
/* Header */
.top{position:sticky;top:0;z-index:20;background:rgba(255,255,255,.92);backdrop-filter:blur(8px);border-bottom:1px solid var(--line);display:flex;justify-content:space-between;align-items:center;padding:.8rem 1.2rem}
.logo{font-family:'Bricolage Grotesque',sans-serif;font-weight:800;font-size:1.25rem}
.logo span{color:var(--accent-d)}
nav a{margin-left:1.1rem;color:var(--ink);text-decoration:none;font-weight:500;font-size:.95rem}
 
/* Hero */
.hero{min-height:88vh;display:flex;align-items:flex-end;color:#fff;padding:2rem 1.2rem 3.5rem;
background:linear-gradient(180deg,rgba(15,22,40,.15),rgba(15,22,40,.8)),url('https://i.ibb.co/Vr5ss1f/erik-mclean-nfo-Ra6-NHTb-U-unsplash.jpg') center/cover,#1f2a44}
.hero-in{max-width:760px;width:100%}
.hero h1{font-size:clamp(2.6rem,10vw,5.5rem);font-weight:800;letter-spacing:-.02em}
.hero p{font-size:clamp(1.05rem,3.5vw,1.35rem);margin:1rem 0 1.6rem;max-width:34ch;opacity:.95}
.btn{background:var(--accent);color:#1b1500;border:0;border-radius:999px;padding:.85rem 1.7rem;font-weight:700;font-size:1rem;text-decoration:none;display:inline-block;transition:background .2s,transform .1s}
.btn:hover{background:#ffbb1f}.btn:active{transform:scale(.97)}
 
/* Products */
section{padding:3.5rem 0}
.wrap{max-width:1100px;margin:0 auto;padding:0 1.2rem}
.head{display:flex;justify-content:space-between;align-items:end;gap:1rem;margin-bottom:1.4rem}
.head h2{font-size:clamp(1.8rem,6vw,2.6rem)}
.head p{color:var(--muted);margin-top:.4rem}
.arrows{display:flex}
.arrows button{width:42px;height:42px;border-radius:50%;border:1px solid var(--line);background:#fff;font-size:1.2rem;margin-left:.4rem}
.arrows button:hover{background:var(--ink);color:#fff}
.track{display:flex;gap:1rem;overflow-x:auto;scroll-snap-type:x mandatory;padding:.3rem 1.2rem 1.2rem;scrollbar-width:thin}
.card{flex:0 0 min(72vw,260px);scroll-snap-align:start;background:var(--card);border:1px solid var(--line);border-radius:var(--r);overflow:hidden;display:flex;flex-direction:column}
.card img{width:100%;aspect-ratio:1;object-fit:cover;background:#eceff6}
.card-b{padding:1rem;display:flex;flex-direction:column;gap:.35rem;flex:1}
.card h3{font-size:1.1rem}
.price{font-weight:700;color:var(--accent-d);font-size:1.1rem}
.card .btn{margin-top:auto;width:100%;text-align:center;padding:.65rem 1rem;background:var(--ink);color:#fff}
.card .btn:hover{background:#34426a}
 
/* About / contact */
.about{background:var(--ink);color:#fff}
.about .wrap{display:grid;gap:2rem}
@media(min-width:760px){.about .wrap{grid-template-columns:1.2fr 1fr}}
.about h2{font-size:clamp(1.8rem,6vw,2.6rem);margin-bottom:.8rem}
.about p{opacity:.85;max-width:52ch}
.about ul{list-style:none;padding:0;display:grid;gap:.7rem;align-content:start}
.about li{border-left:3px solid var(--accent);padding-left:.8rem}
.about a{color:var(--accent)}
footer{text-align:center;padding:1.5rem;color:var(--muted);font-size:.9rem}
 
/* Floating buttons */
.fab{position:fixed;right:1rem;z-index:30;width:56px;height:56px;border-radius:50%;border:0;display:grid;place-items:center;box-shadow:0 6px 18px rgba(0,0,0,.25);text-decoration:none}
#wa{bottom:1rem;background:var(--wa)}
#cartBtn{bottom:5rem;background:var(--accent);color:#1b1500}
.fab svg{width:28px;height:28px}
#count{position:absolute;top:-4px;right:-4px;background:#d93636;color:#fff;font-size:.75rem;font-weight:700;min-width:22px;height:22px;border-radius:11px;display:grid;place-items:center;padding:0 5px}
#cartBtn.bump{animation:bump .35s}
@keyframes bump{50%{transform:scale(1.2)}}
 
/* Cart drawer */
.overlay{position:fixed;inset:0;background:rgba(10,15,30,.5);z-index:40;opacity:0;pointer-events:none;transition:opacity .25s}
.overlay.open{opacity:1;pointer-events:auto}
.drawer{position:fixed;top:0;right:0;bottom:0;width:min(100%,430px);background:#fff;z-index:50;transform:translateX(100%);transition:transform .3s;display:flex;flex-direction:column}
.drawer.open{transform:none}
.dhead{display:flex;justify-content:space-between;align-items:center;padding:.8rem 1.2rem;border-bottom:1px solid var(--line)}
.dhead h2{font-size:1.3rem}
.x{background:none;border:0;font-size:1.8rem;line-height:1}
.dbody{flex:1;overflow-y:auto;padding:1rem 1.2rem}
.empty{color:var(--muted);text-align:center;padding:2rem 0}
.item{display:flex;gap:.8rem;align-items:center;padding:.7rem 0;border-bottom:1px solid var(--line)}
.item img{width:56px;height:56px;border-radius:10px;object-fit:cover}
.item .i{flex:1;min-width:0}.item .i b{display:block}.item .i small{color:var(--muted)}
.qty{display:flex;align-items:center;gap:.4rem}
.qty button{width:28px;height:28px;border-radius:50%;border:1px solid var(--line);background:#fff}
.total{display:flex;justify-content:space-between;font-weight:700;font-size:1.15rem;padding:1rem 0}
form{display:grid;gap:.7rem;border-top:2px solid var(--ink);padding-top:1rem}
form h3{font-size:1.1rem}
label{font-size:.88rem;font-weight:500;display:grid;gap:.25rem}
input,textarea{font:inherit;padding:.65rem .8rem;border:1px solid #c9cfdf;border-radius:10px;width:100%}
textarea{resize:vertical;min-height:60px}
.err{color:#d93636;font-size:.88rem;min-height:1.2em}
.row{display:grid;gap:.5rem}
.btn.alt{background:var(--wa);color:#05260f}
.toast{position:fixed;left:50%;bottom:1.2rem;transform:translate(-50%,200%);background:var(--ink);color:#fff;padding:.8rem 1.2rem;border-radius:12px;z-index:60;transition:transform .3s;max-width:90vw;text-align:center}
.toast.show{transform:translate(-50%,0)}
@media(prefers-reduced-motion:reduce){*{animation:none!important;transition:none!important;scroll-behavior:auto!important}}
</style>
</head>
<body>
 
<div class="top">
  <div class="logo">the local <span>shop</span></div>
  <nav><a href="#products">Products</a><a href="#contact">Contact</a></nav>
</div>
 
<main>
  <div class="hero">
    <div class="hero-in">
      <h1>Fresh Finds, Best Prices</h1>
      <p>Everyday essentials from your neighbourhood shop. Pick what you need and we'll get it ready for you.</p>
      <a class="btn" href="#products">Shop Now</a>
    </div>
  </div>
 
  <section id="products">
    <div class="wrap head">
      <div><h2>Our products</h2><p>Swipe to browse. Tap Add to Cart to start your order.</p></div>
      <div class="arrows"><button id="prev" aria-label="Previous products">‹</button><button id="next" aria-label="Next products">›</button></div>
    </div>
    <div class="track" id="track" tabindex="0" aria-label="Product carousel"></div>
  </section>
 
  <section class="about" id="contact">
    <div class="wrap">
      <div>
        <h2>Visit or message us</h2>
        <p>The Local Shop is your neighbourhood store for quality goods at fair prices. Place an order here, or message us on WhatsApp and we'll confirm availability.</p>
      </div>
      <ul>
        <li>WhatsApp: <a href="https://wa.me/9322441863">9322441863</a></li>
        <li>Email: <a href="mailto:sachinmudavath38@gmail.com">sachinmudavath38@gmail.com</a></li>
        <li>Add your address and opening hours here</li>
      </ul>
    </div>
  </section>
</main>
<footer>© <span id="yr"></span> The Local Shop</footer>
 
<!-- Floating buttons -->
<button class="fab" id="cartBtn" aria-label="Open cart">
  <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="9" cy="21" r="1"/><circle cx="20" cy="21" r="1"/><path d="M1 1h4l2.7 13.4a2 2 0 0 0 2 1.6h9.7a2 2 0 0 0 2-1.6L23 6H6"/></svg>
  <span id="count">0</span>
</button>
<a class="fab" id="wa" href="https://wa.me/9322441863" target="_blank" rel="noopener" aria-label="Chat on WhatsApp">
  <svg viewBox="0 0 24 24" fill="#fff"><path d="M12 2a10 10 0 0 0-8.6 15L2 22l5.2-1.4A10 10 0 1 0 12 2zm5.5 14.2c-.2.6-1.3 1.2-1.8 1.2-.5.1-1 .2-3.3-.7a11 11 0 0 1-4.600-4 5 5 0 0 1-1-2.700c0-1.300.7-1.900.9-2.200.2-.3.5-.3.7-.3h.5c.2 0 .4 0 .6.500l.8 2c.1.200.1.400 0 .5l-.4.600-.4.400c-.1.200-.3.300-.1.600a7 7 0 0 0 3.200 2.800c.3.200.5.100.700-.1l.9-1c.2-.2.400-.2.600-.1l2 1c.3.100.5.200.5.300.1.200.1.800-.1 1.400z"/></svg>
</a>
 
<!-- Cart drawer with order form -->
<div class="overlay" id="overlay"></div>
<aside class="drawer" id="drawer" aria-label="Your cart" aria-hidden="true">
  <div class="dhead"><h2>Your cart</h2><button class="x" id="closeCart" aria-label="Close cart">×</button></div>
  <div class="dbody">
    <div id="items"></div>
    <div class="total"><span>Total</span><span id="total">₹0</span></div>
    <form id="orderForm" novalidate>
      <h3>Your details</h3>
      <label>Full name<input id="cname" autocomplete="name" required></label>
      <label>Phone number<input id="cphone" type="tel" autocomplete="tel" inputmode="tel" placeholder="e.g. 9876543210" required></label>
      <label>Address or note (optional)<textarea id="cnote"></textarea></label>
      <div class="err" id="err" role="alert"></div>
      <div class="row">
        <button class="btn" type="submit">Send order by email</button>
        <button class="btn alt" type="button" id="waOrder">Send order on WhatsApp</button>
      </div>
    </form>
  </div>
</aside>
<div class="toast" id="toast" role="status"></div>
 
<script>
/* ===== EDIT YOUR PRODUCTS HERE =====
   Replace each img value with your own product image URL.
   Leave img as "" to show a colour placeholder. */
const OWNER_EMAIL = "sachinmudavath38@gmail.com";
const WA_NUMBER = "9322441863";
const CURRENCY = "₹";
const PRODUCTS = [
  {id:1,name:"Product One",price:199,img:""},
  {id:2,name:"Product Two",price:249,img:""},
  {id:3,name:"Product Three",price:99,img:""},
  {id:4,name:"Product Four",price:349,img:""},
  {id:5,name:"Product Five",price:149,img:""},
  {id:6,name:"Product Six",price:299,img:""}
];
 
const $ = id => document.getElementById(id);
const cart = {}; // id -> qty
const colors = ["#f2a900","#4c6ef5","#12b886","#e8590c","#ae3ec9","#1098ad"];
const money = n => CURRENCY + n.toLocaleString("en-IN");
const esc = s => String(s).replace(/[&<>"]/g, c => ({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;"}[c]));
 
function imgFor(p){
  if(p.img) return p.img;
  const c = colors[(p.id-1)%colors.length];
  const svg = `<svg xmlns='http://www.w3.org/2000/svg' width='400' height='400'><rect width='400' height='400' fill='${c}' opacity='.25'/><text x='200' y='225' font-size='90' text-anchor='middle' fill='${c}' font-family='sans-serif' font-weight='700'>${p.id}</text></svg>`;
  return "data:image/svg+xml;utf8," + encodeURIComponent(svg);
}
 
/* Render products */
$("track").innerHTML = PRODUCTS.map(p => `
  <article class="card">
    <img src="${esc(imgFor(p))}" alt="${esc(p.name)}" loading="lazy">
    <div class="card-b">
      <h3>${esc(p.name)}</h3>
      <div class="price">${money(p.price)}</div>
      <button class="btn" data-add="${p.id}">Add to Cart</button>
    </div>
  </article>`).join("");
 
/* Carousel: arrows + gentle auto-slide (stops when the visitor interacts) */
const track = $("track");
const step = () => track.querySelector(".card").offsetWidth + 16;
function slide(d){
  const max = track.scrollWidth - track.clientWidth;
  if(d>0 && track.scrollLeft >= max-4) track.scrollTo({left:0,behavior:"smooth"});
  else track.scrollBy({left:d*step(),behavior:"smooth"});
}
$("next").onclick = () => slide(1);
$("prev").onclick = () => slide(-1);
let auto = setInterval(()=>slide(1), 4000);
const stop = () => clearInterval(auto);
["pointerdown","mouseenter","focusin"].forEach(e => track.addEventListener(e, stop));
if(matchMedia("(prefers-reduced-motion:reduce)").matches) stop();
 
/* Cart */
const find = id => PRODUCTS.find(p => p.id == id);
function render(){
  const ids = Object.keys(cart);
  $("count").textContent = ids.reduce((s,i)=>s+cart[i],0);
  $("items").innerHTML = ids.length ? ids.map(i => { const p = find(i); return `
    <div class="item">
      <img src="${esc(imgFor(p))}" alt="">
      <div class="i"><b>${esc(p.name)}</b><small>${money(p.price)} each</small></div>
      <div class="qty"><button data-dec="${i}" aria-label="Remove one">−</button><span>${cart[i]}</span><button data-inc="${i}" aria-label="Add one">+</button></div>
    </div>`; }).join("") : `<p class="empty">Your cart is empty. Add a product to get started.</p>`;
  $("total").textContent = money(ids.reduce((s,i)=>s+cart[i]*find(i).price,0));
}
function toast(msg){const t=$("toast");t.textContent=msg;t.classList.add("show");clearTimeout(t._t);t._t=setTimeout(()=>t.classList.remove("show"),2600)}
 
document.addEventListener("click", e => {
  const b = e.target.closest("button"); if(!b) return;
  if(b.dataset.add){cart[b.dataset.add]=(cart[b.dataset.add]||0)+1;render();toast(find(b.dataset.add).name+" added to cart");const c=$("cartBtn");c.classList.remove("bump");void c.offsetWidth;c.classList.add("bump")}
  if(b.dataset.inc){cart[b.dataset.inc]++;render()}
  if(b.dataset.dec){if(--cart[b.dataset.dec]<=0)delete cart[b.dataset.dec];render()}
});
 
const openCart = o => {$("drawer").classList.toggle("open",o);$("overlay").classList.toggle("open",o);$("drawer").setAttribute("aria-hidden",String(!o))};
$("cartBtn").onclick = () => openCart(true);
$("closeCart").onclick = $("overlay").onclick = () => openCart(false);
document.addEventListener("keydown", e => e.key==="Escape" && openCart(false));
 
/* Build order text + validate */
function buildOrder(){
  const name = $("cname").value.trim(), phone = $("cphone").value.trim(), note = $("cnote").value.trim();
  const ids = Object.keys(cart);
  const err = $("err"); err.textContent = "";
  if(!ids.length){err.textContent="Your cart is empty. Add at least one product.";return null}
  if(!name){err.textContent="Enter your full name.";$("cname").focus();return null}
  if(!/^[+\d][\d\s-]{6,}$/.test(phone)){err.textContent="Enter a valid phone number.";$("cphone").focus();return null}
  const lines = ids.map((i,k)=>`${k+1}. ${find(i).name} x ${cart[i]} = ${money(find(i).price*cart[i])}`);
  const total = money(ids.reduce((s,i)=>s+cart[i]*find(i).price,0));
  return `New order from The Local Shop website\n\nCustomer name: ${name}\nPhone number: ${phone}\n\nItems:\n${lines.join("\n")}\n\nTotal: ${total}` + (note?`\n\nAddress/Note: ${note}`:"");
}
 
$("orderForm").addEventListener("submit", e => {
  e.preventDefault();
  const body = buildOrder(); if(!body) return;
  location.href = `mailto:${OWNER_EMAIL}?subject=${encodeURIComponent("New order – "+$("cname").value.trim())}&body=${encodeURIComponent(body)}`;
  toast("Opening your email app. Press Send to place the order.");
});
$("waOrder").onclick = () => {
  const body = buildOrder(); if(!body) return;
  window.open(`https://wa.me/${WA_NUMBER}?text=${encodeURIComponent(body)}`,"_blank","noopener");
};
 
$("yr").textContent = new Date().getFullYear();
render();
</script>
</body>
</html>
 
