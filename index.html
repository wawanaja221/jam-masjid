<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Jadwal Sholat + Audio Scheduler</title>

<style>

body{
background:black;
color:red;
font-family:monospace;
margin:0;
text-align:center;
}

#judul{font-size:50px;margin-top:20px;color:orange;}
#tanggal{font-size:30px;color:cyan;margin-top:10px;}
#jam{font-size:120px;margin-top:25px;color:orange;}
#imam{font-size:30px;color:white;margin-top:10px;}
#kalenderJawa{font-size:28px;color:lime;margin-top:10px;}
#countdown{font-size:40px;color:white;margin-top:200px;}
#jadwal{font-size:30px;color:yellow;margin-top:50px;}

#adzan{
display:none;
position:absolute;
top:50%;
width:100%;
font-size:80px;
color:lime;
}

#settingBtn{
position:fixed;
bottom:10px;
right:10px;
padding:6px 10px;
cursor:pointer;
}

#audioPanel{
display:none;
position:fixed;
bottom:50px;
right:10px;
background:#111;
padding:10px;
border:1px solid #555;
max-height:400px;
overflow:auto;
color:white;
}

</style>
</head>

<body>

<div id="judul">JADWAL SHOLAT</div>
<div id="tanggal"></div>
<div id="jam"></div>
<div id="imam">MASTER IMAM : ......</div>
<div id="kalenderJawa"></div>
<div id="countdown"></div>
<div id="adzan"></div>

<div id="jadwal">
Imsak 04:07 | Subuh 04:18 | Dzuhur 11:37 <br>
Ashar 14:50 | Maghrib 17:37 | Isya 18:47
</div>

<button id="startBtn">Mulai Jam</button>
<button id="settingBtn">⚙</button>

<div id="audioPanel">
<h3>Audio Scheduler</h3>
<div id="audioBlocks"></div>
</div>

<audio id="player"></audio>

<script>

// ================= AUDIO =================

let audioCtx=null

function beep(freq,dur){

let osc=audioCtx.createOscillator()
osc.type="sine"
osc.frequency.value=freq
osc.connect(audioCtx.destination)

osc.start()
setTimeout(()=>osc.stop(),dur)

}

// ================= JADWAL =================

let jadwal=[
{nama:"Subuh",waktu:"04:18"},
{nama:"Dzuhur",waktu:"11:37"},
{nama:"Ashar",waktu:"14:50"},
{nama:"Maghrib",waktu:"17:37"},
{nama:"Isya",waktu:"18:47"}
]

let beepDone={}
let adzanDone={}

// ================= CEK ADZAN =================

function cekAdzan(){

let now=new Date()

let jam=now.getHours()
let menit=now.getMinutes()
let detik=now.getSeconds()

jadwal.forEach(item=>{

let t=item.waktu.split(":")
let j=parseInt(t[0])
let m=parseInt(t[1])

if(detik==10){
beepDone[item.nama]=false
adzanDone[item.nama]=false
}

// beep sebelum adzan
if(jam==j && menit==m-1 && detik==57 && !beepDone[item.nama]){

beepDone[item.nama]=true

for(let i=0;i<3;i++){
setTimeout(()=>beep(700,120),i*400)
}

}

// beep panjang adzan
if(jam==j && menit==m && detik==0 && !adzanDone[item.nama]){

adzanDone[item.nama]=true

beep(1000,4000)

tampilAdzan(item.nama)

}

})

}

// ================= TAMPIL ADZAN =================

function tampilAdzan(nama){

let adzan=document.getElementById("adzan")

adzan.innerHTML="WAKTU ADZAN "+nama.toUpperCase()
adzan.style.display="block"

setTimeout(()=>{
adzan.style.display="none"
},10000)

}

// ================= JAM =================

function updateJam(){

let now=new Date()

let j=now.getHours().toString().padStart(2,"0")
let m=now.getMinutes().toString().padStart(2,"0")
let d=now.getSeconds().toString().padStart(2,"0")

document.getElementById("jam").innerHTML=j+":"+m+":"+d

}

// ================= TANGGAL =================

function updateTanggal(){

let now=new Date()

let hijri=new Intl.DateTimeFormat('id-TN-u-ca-islamic',{
day:'numeric',month:'long',year:'numeric'
}).format(now)

let masehi=now.toLocaleDateString('id-ID',{
weekday:'long',day:'numeric',month:'long',year:'numeric'
})

document.getElementById("tanggal").innerHTML=masehi+" | "+hijri

}

// ================= PASARAN JAWA =================

function getPasaranJawa(){

let now=new Date()

let pasaran=["Legi","Pahing","Pon","Wage","Kliwon"]

let tglAwal=new Date(1970,0,1)

let selisih=Math.floor((now-tglAwal)/(1000*60*60*24))

let index=(selisih+3)%5

document.getElementById("kalenderJawa").innerHTML="Pasaran: "+pasaran[index]

}

// ================= COUNTDOWN =================

function updateCountdown(){

let now=new Date()

let next=null
let nama=""

for(let i=0;i<jadwal.length;i++){

let waktu=new Date()
let t=jadwal[i].waktu.split(":")

waktu.setHours(t[0],t[1],0)

if(waktu>now){

next=waktu
nama=jadwal[i].nama
break

}

}

if(next==null){

let t=jadwal[0].waktu.split(":")

next=new Date()
next.setDate(next.getDate()+1)
next.setHours(t[0],t[1],0)

nama=jadwal[0].nama

}

let selisih=next-now

let jam=Math.floor(selisih/3600000)
let menit=Math.floor((selisih%3600000)/60000)
let detik=Math.floor((selisih%60000)/1000)

document.getElementById("countdown").innerHTML=
"Menuju "+nama+" "+jam+":"+menit+":"+detik

}

// ================= AUDIO SCHEDULER =================

const dayNames=["Minggu","Senin","Selasa","Rabu","Kamis","Jumat","Sabtu"]
const audioBlocksDiv=document.getElementById("audioBlocks")

const audios=[]

for(let i=0;i<7;i++){

const div=document.createElement("div")

div.innerHTML=`

<hr>
Audio ${i+1}<br>

<input type="file" class="audioFile" accept=".mp3"><br>

${dayNames.map((d,j)=>`<label><input type="checkbox" class="day${i}" value="${j}">${d}</label>`).join("")}

<br>

<input type="time" class="timeInput${i}" step="1">

<audio id="playerExtra${i}"></audio>

`

audioBlocksDiv.appendChild(div)

audios.push({
player:document.getElementById(`playerExtra${i}`),
file:null,
days:[],
time:null
})

}

document.querySelectorAll(".audioFile").forEach((input,idx)=>{

input.addEventListener("change",e=>{

audios[idx].file=URL.createObjectURL(e.target.files[0])
audios[idx].player.src=audios[idx].file

})

})

for(let i=0;i<7;i++){

const checkboxes=document.querySelectorAll(`.day${i}`)

checkboxes.forEach(cb=>{

cb.addEventListener("change",()=>{

audios[i].days=Array.from(checkboxes)
.filter(chk=>chk.checked)
.map(chk=>parseInt(chk.value))

})

})

}

for(let i=0;i<7;i++){

const timeInput=document.querySelector(`.timeInput${i}`)

timeInput.addEventListener("change",e=>{

const p=e.target.value.split(":").map(Number)

audios[i].time={hour:p[0],minute:p[1],second:p[2]||0}

})

}

function cekAudioTambahan(){

let now=new Date()

audios.forEach(audio=>{

if(!audio.file||!audio.days.length||!audio.time)return

if(
audio.days.includes(now.getDay()) &&
now.getHours()==audio.time.hour &&
now.getMinutes()==audio.time.minute &&
now.getSeconds()==audio.time.second
){

audio.player.play()

}

})

}

// ================= START =================

document.getElementById("startBtn").onclick=function(){

audioCtx=new AudioContext()

updateJam()
updateTanggal()
getPasaranJawa()

setInterval(updateJam,1000)
setInterval(updateTanggal,60000)
setInterval(getPasaranJawa,60000)
setInterval(updateCountdown,1000)
setInterval(cekAdzan,1000)
setInterval(cekAudioTambahan,1000)

this.style.display="none"

}

// ================= SETTING =================

document.getElementById("settingBtn").onclick=()=>{

let panel=document.getElementById("audioPanel")

panel.style.display=panel.style.display=="none"?"block":"none"

}

</script>

</body>
</html>
