<!DOCTYPE html><html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TokoKeren</title>
<style>
body{font-family:Arial;margin:0;background:#f5f5f5}
header{background:#111;color:#fff;padding:15px;text-align:center;font-size:20px}
.container{padding:15px}
.products{display:grid;grid-template-columns:repeat(auto-fit,minmax(150px,1fr));gap:15px}
.card{background:#fff;padding:10px;border-radius:10px;box-shadow:0 2px 5px rgba(0,0,0,0.1)}
.card img{width:100%;border-radius:10px}
.card h3{margin:5px 0}
.btn{background:#111;color:#fff;padding:8px;border:none;border-radius:5px;cursor:pointer;width:100%}
.cart{position:fixed;bottom:0;left:0;right:0;background:#fff;padding:10px;border-top:1px solid #ccc}
</style>
</head>
<body><header>🛒 TokoKeren</header><div class="container">
<div class="products" id="productList"></div>
</div><div class="cart">
Keranjang: <span id="cartCount">0</span> item
</div><script>
const products=[
{name:"Sepatu Keren",price:150000,img:"https://via.placeholder.com/150"},
{name:"Kaos Style",price:80000,img:"https://via.placeholder.com/150"},
{name:"Jaket Trendy",price:200000,img:"https://via.placeholder.com/150"}
];

let cart=0;

const list=document.getElementById("productList");

products.forEach(p=>{
let el=document.createElement("div");
el.className="card";
el.innerHTML=`
<img src="${p.img}">
<h3>${p.name}</h3>
<p>Rp ${p.price}</p>
<button class="btn">Beli</button>
`;

el.querySelector("button").onclick=()=>{
cart++;
document.getElementById("cartCount").innerText=cart;
alert("Ditambahkan ke keranjang!");
};

list.appendChild(el);
});
</script></body>
</html>
