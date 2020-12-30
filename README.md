# denasour-game
the second game i made it  in one day   it is like google  game




const canvas = document.querySelector("canvas")
const div = document.getElementById("youtube")
const canvas2 = document.createElement("canvas")
const chraracter = document.getElementById("character")
const start = document.getElementById("start")
const score   = document.getElementById("score")

document.body.appendChild(canvas2)

let ctx = canvas2.getContext("2d")

canvas2.setAttribute("class","canvas2")

const mydiv = document.createElement("div")

document.body.appendChild(mydiv)

mydiv.setAttribute("class","mydiv")

canvas.width = 600

canvas.height = 600 - 150

let context = canvas.getContext("2d")
let couple = []
let i = 0
let w= 120
let prins = 400
let y = Math.floor(Math.random()*300) -100
let anothey = Math.floor(Math.random() * 300) + 50

let x = 0


for(;i<5;i++){
 couple.push(context)
}

couple[0].fillRect(x+50,y+150,w,prins)

couple[1].fillRect(x+180, y+170,w,prins)

couple[2].fillRect(x+300, y +170,w,prins)

couple[3].fillRect(x+430,anothey+20,w,prins)

let  couple1  = []
let m = 0
for(;m<28;m++){
    let google = document.createElement("div")
    mydiv.appendChild(google)
    google.setAttribute("class","google")
}
let k = 0
let couple2 = []


e = 0
for(;e<5;e++){
    let game  = document.createElement("div")
    div.appendChild(game)
    game.setAttribute("class","fiverr")
}
const car = document.getElementById("car")

function create(){
    let bottom  = 0
    let measure = car.style.right
    bottom = 715
    car.style.right = bottom +"px"
    car.style.transition = "2s"
    if(measure  == bottom +"px"){
        car.style.right = "-120" +"px"
        car.style.transition = "none"
    }
}
setInterval(create,  2000)
const car2 = document.getElementById("car2") 
function anothercreate(){
    let right  = 0
    let anothermeasure = car.style.right
    right = 715
    car2.style.right = right +"px"
    car2.style.transition = "1.5s"
    if(anothermeasure  == right +"px"){
        car2.style.right = "-120" +"px"
        car2.style.transition = "none"
    }
}
setInterval(anothercreate,1500)
function visible(){
    let car3  = parseInt( getComputedStyle(car2).getPropertyValue("right") ) 
    if(car3 == -120 ){
        car2.style.visibility  = "hidden"
    }
    if(car3 > -89){
        car2.style.visibility = "visible"
    }  
}
setInterval(visible,10)
function hidden(){
    let car1  = parseInt( getComputedStyle(car).getPropertyValue("right") ) 
    if(car1 == -120){
        car.style.visibility  = "hidden"
    }
    if(car1 > -89){
        car.style.visibility = "visible"
    }
}
setInterval(hidden,10)

let topping  = 0
function down(){
    let anothersamething = parseInt( getComputedStyle(chraracter).getPropertyValue("bottom") )
    let gravity = 0
    if(anothersamething == 100){
        chraracter.style.bottom  = "2px"
        chraracter.style.transition = '0.1s'
    }
}
setInterval(down,100)

function up(){
    let samething =parseInt(  getComputedStyle(chraracter).getPropertyValue("bottom") )
    topping  = 100
    if(samething == 2){
        chraracter.style.bottom = "100px"
        chraracter.style.transition = "0.3s"
    }
    console.log(samething)
}
function func(event){
    if(event.keyCode == "38" || event.keyCode ==  "32"){
        up()
    }
}



function final(){
    let measure =  parseInt( getComputedStyle(car).getPropertyValue("left") )
    let measure1  = parseInt ( getComputedStyle(car2).getPropertyValue("left") )  
    let chraracter1 = parseInt( getComputedStyle(chraracter).getPropertyValue("bottom") )
    if(chraracter1 < 50  && measure <  60 && measure > 0 ){
        alert("you lose")
        score.textContent = 0
    }
    if(chraracter1  < 50  && measure1  < 60 && measure1 > 0 ){
        alert("you lose")
        score.textContent = 0
    }
    console.log(measure1)

}


start.addEventListener('click',function(){
    setInterval(function(){
        score.textContent++
    },300)
    start.style.display = "none"
    document.addEventListener("keydown", func)
    setInterval(final,10)

})
