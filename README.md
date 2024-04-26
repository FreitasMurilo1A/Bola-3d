let cor;
let posicaoHorizontal; // x
let posicaoVertical; // y
let diametro = 50;

function setup() {
  createCanvas(800, 600);
  background(color(100,0,0));
  cor = color(random(0,255), random(0,255), random(0,255));
  posicaoHorizontal = 200;
  posicaoVertical = 200;
}

function draw() {
  fill(cor);
  circle(posicaoHorizontal, posicaoVertical, diametro);

  if (mouseX < posicaoHorizontal){
    posicaoHorizontal = posicaoHorizontal - 1;
  } else if (mouseX > posicaoHorizontal){
    posicaoHorizontal = posicaoHorizontal + 1;
  }

  if (mouseY < posicaoVertical){
    posicaoVertical--;
  } else if (mouseY > posicaoVertical){
    posicaoVertical++;
  }

  if (mouseIsPressed){
    cor = color(random(0,255), random(0,255), random(0,255), random(0,100));
  }
}

function mouseWheel(event) {
  let delta = event.delta;
  if (delta > 0) {
    diametro += 5;
  } else {
    diametro -= 5;
    diametro = max(10, diametro); // Garante que o diâmetro nunca seja menor que 10
  }
}
