# Nni-specials
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>For Nni ❤️</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body{
    margin:0;
    font-family:'Segoe UI',sans-serif;
    background:radial-gradient(circle at top,#4b2416,#120805);
    color:#fff;
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    overflow:hidden;
}
.card{
    background:rgba(255,255,255,0.12);
    padding:28px;
    border-radius:24px;
    max-width:380px;
    text-align:center;
    box-shadow:0 0 40px rgba(255,165,90,0.25);
    animation:fadeIn 1.5s;
}
.hidden{display:none;}
h1{font-size:26px;margin-bottom:10px;}
p{font-size:16px;line-height:1.7;}
input{
    padding:12px;
    width:80%;
    border-radius:20px;
    border:none;
    text-align:center;
}
button{
    margin-top:16px;
    padding:12px 24px;
    border-radius:25px;
    border:none;
    font-size:15px;
    background:linear-gradient(135deg,#ff9f43,#ff6f00);
    color:#3b1f12;
    cursor:pointer;
}
.emojiBtn{
    font-size:38px;
    margin:10px;
    cursor:pointer;
}
.counter{
    margin-top:10px;
    color:#ffddaa;
    font-size:14px;
}
.float{
    position:absolute;
    bottom:-20px;
    font-size:22px;
    animation:floatUp 7s linear;
}
@keyframes floatUp{
    0%{transform:translateY(0);opacity:1;}
    100%{transform:translateY(-120vh);opacity:0;}
}
@keyframes fadeIn{
    from{opacity:0;transform:scale(0.9);}
    to{opacity:1;transform:scale(1);}
}
</style>
</head>

<body>

<audio autoplay loop>
  <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-4.mp3" type="audio/mpeg">
</audio>

<!-- LOCK -->
<div class="card" id="lock">
    <h1>🔒 Only for Nni</h1>
    <p>When I have gave you first chocolate</p>
    <input id="answer" placeholder="Answer">
    <br>
    <button onclick="unlock()">Unlock ❤️</button>
</div>

<!-- LEVEL 1 -->
<div class="card hidden" id="level1">
    <h1>Level 1 🍫 Chocolate</h1>
    <p>Collect 5 chocolates to continue</p>
    <div>
        <span class="emojiBtn" onclick="collect(1)">🍫</span>
        <span class="emojiBtn" onclick="collect(1)">🍫</span>
        <span class="emojiBtn" onclick="collect(1)">🍫</span>
    </div>
    <div class="counter">Collected: <span id="c1">0</span> / 5</div>
</div>

<!-- LEVEL 2 -->
<div class="card hidden" id="level2">
    <h1>Level 2 🫂 Hugs</h1>
    <p>Collect 5 hugs from Beboo</p>
    <div>
        <span class="emojiBtn" onclick="collect(2)">🫂</span>
        <span class="emojiBtn" onclick="collect(2)">❤️</span>
        <span class="emojiBtn" onclick="collect(2)">🫂</span>
    </div>
    <div class="counter">Collected: <span id="c2">0</span> / 5</div>
</div>

<!-- LEVEL 3 -->
<div class="card hidden" id="level3">
    <h1>Level 3 ♾ Forever</h1>
    <p>Tap love 3 times to unlock my heart</p>
    <div>
        <span class="emojiBtn" onclick="collect(3)">❤️</span>
        <span class="emojiBtn" onclick="collect(3)">❤️</span>
    </div>
    <div class="counter">Collected: <span id="c3">0</span> / 3</div>
</div>

<!-- FINAL -->
<div class="card hidden" id="final">
    <h1>Happy Chocolate Day ❤️</h1>
    <p>
        Nni… 🥺  
        Every level of this game  
        is just one small part of what I feel for you 💖  
        Chocolates, hugs, forever —  
        everything leads to you.
    </p>
    <p>
        Distance can’t stop us.  
        My heart already lives with you ❤️
    </p>
    <p style="color:#ffbe76;margin-top:15px;">
        Always yours,<br>
        <b>— Beboo 💕</b>
    </p>
</div>

<script>
function unlock(){
    const a=document.getElementById("answer").value
    .toLowerCase().replace(/\s+/g,"");
    if(["19november","19-11","19/11"].includes(a)){
        lock.style.display="none";
        level1.classList.remove("hidden");
    }
}

let l1=0,l2=0,l3=0;
function collect(level){
    if(level===1){
        l1++; c1.innerText=l1;
        if(l1>=5){ level1.style.display="none"; level2.classList.remove("hidden"); }
    }
    if(level===2){
        l2++; c2.innerText=l2;
        if(l2>=5){ level2.style.display="none"; level3.classList.remove("hidden"); }
    }
    if(level===3){
        l3++; c3.innerText=l3;
        if(l3>=3){ level3.style.display="none"; final.classList.remove("hidden"); }
    }
}

setInterval(()=>{
    const e=document.createElement("div");
    e.className="float";
    e.innerHTML=Math.random()>0.5?"❤️":"🍫";
    e.style.left=Math.random()*100+"vw";
    document.body.appendChild(e);
    setTimeout(()=>e.remove(),7000);
},400);
</script>

</body>
</html>
