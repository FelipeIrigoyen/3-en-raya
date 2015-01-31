
boolean x11;
boolean x12;
boolean x13;

boolean x21;
boolean x22;
boolean x23;

boolean x31;
boolean x32;
boolean x33;

boolean o11;
boolean o12;
boolean o13;

boolean o21;
boolean o22;
boolean o23;

boolean o31;
boolean o32;
boolean o33;

boolean iniciar = false;
boolean juegoActivo;

void setup() {
  size(300, 300);
  background(#C9BAB1);
 }
void draw() { 
  if(iniciar == false){
    fill(#502D18);
    textSize(22);
  text("TRES EN RAYA", 65, 45);
  textSize(11);
  fill(#342A24);
  text("Presione i ó I para Iniciar el Juego", 50, 120);
  text("Presione n ó N para Comenzar un Juego Nuevo", 20, 140);
  fill(#502D18);
    textSize(16);
  text("Click Izquierdo X      Click derecho O", 7, 180);
   textSize(11);
  fill(#342A24);
  text("Creado por: Felipe Irigoyen", 140, 280);
  
  if (keyPressed) {
    if (key == 'i' || key == 'I')
    background(0);
    iniciar = true;
    
    }
  
  
  }else{
  stroke(#502D18);  
  strokeWeight(5); 
  line(width/3, 0, width/3, height);
  line(width*2/3, 0, width*2/3, height);
  line(0, height/3, width, height/3);
  line(0, height*2/3, width, height*2/3);
  juegoActivo = true;
}
  
  
  if(juegoActivo == true){
  if (mousePressed && (mouseButton == LEFT)) { 
     stroke(#3B1D0B); 
     strokeWeight(3);
    //Casilla 1-1
    if (mouseX<width/3 && mouseY<height/3) {
      line(10, 10, (width/3)-10, (height/3)-10);
      line(10, (height/3)-10, (width/3)-10, 10 );
      x11 = true;
    }
    //Casilla 1-2
    if (mouseX<width*2/3 && mouseX>width/3 && mouseY<height/3) {
      line((width/3)+10, 10, (width*2/3)-10, (height/3)-10);
      line((width/3)+10, (height/3)-10, (width*2/3)-10, 10);
      x12 = true;
    }
    //Casilla 1-3
    if (mouseX>width*2/3 && mouseY<height/3) {
      line(((width)-width/3)+10, 10, width-10, (height/3)-10);
      line(((width)-width/3)+10, (height/3)-10, width-10, 10);
      x13 = true;
    }
    //Casilla 2-1
    if (mouseX<width/3 && mouseY>height/3 && mouseY<height*2/3) {
      line(10, (height/3)+10, (width/3)-10, (height*2/3)-10);
      line(10, (height*2/3)-10, (width/3)-10, (height/3)+10 );
      x21 = true;
    }
    //casilla 2-2
    if (mouseX>width/3 && mouseX<width*2/3 && mouseY>height/3 && mouseY<height*2/3) {
      line((width/3)+10, (height/3)+10, (width*2/3)-10, (height*2/3)-10);
      line((width/3)+10, (height*2/3)-10, (width*2/3)-10, (height/3)+10);
      x22 = true;
    }
    //Casilla 2-3
    if (mouseX>width*2/3 && mouseY>height/3 && mouseY<height*2/3) {
      line((width*2/3)+10, (height/3)+10, width-10, (height*2/3)-10);
      line((width*2/3)+10, (height*2/3)-10, width-10, (height/3)+10);
      x23 = true;
    }
    //Casilla 3-1
    if (mouseX<width/3 && mouseY>height*2/3 ) {
      line(10, (height*2/3)+10, (width/3)-10, height-10);
      line(10, height-10, (width/3)-10, (height*2/3)+10);
      x31 = true;
    }
    //Casilla 3-2
    if (mouseX>width/3 && mouseX<width*2/3 && mouseY>height*2/3) {
      line((width/3)+10, (height*2/3)+10, (width*2/3)-10, height-10);
      line((width/3)+10, height-10, (width*2/3)-10, (height*2/3)+10);
      x32 = true;
    }
    //Casilla 3-3
    if (mouseX>width*2/3 && mouseY>height*2/3) {
      line((width*2/3)+10, (height*2/3)+10, width-10, height-10);
      line((width*2/3)+10, height-10, width-10, (height*2/3)+10);
      x33 = true;
    }
    
    
    
  }

  
  
  
  if (mousePressed && (mouseButton == RIGHT)) {   
    stroke(#271003); 
    strokeWeight(4); 
    fill(0);  
    //Casilla 1-1
    if (mouseX<width/3 && mouseY<height/3) {
      ellipse(width/6, height/6, (width/3.5)-5, (height/3.5)-5);
      o11 = true;
    }
    //Casilla 1-2
    if (mouseX<width*2/3 && mouseX>width/3 && mouseY<height/3) {
      ellipse(width/2, height/6, (width/3.5)-5, (height/3.5)-5);
      o12 = true;
    }
    //Casilla 1-3
    if (mouseX>width*2/3 && mouseY<height/3) {
      ellipse(width-width/6, height/6, (width/3.5)-5, (height/3.5)-5);
      o13 = true;
    }
    //Casilla 2-1
    if (mouseX>width*2/3 && mouseY>height/3 && mouseY<height*2/3){
      ellipse(width-width/6, height/2, (width/3.5)-5, (height/3.5)-5);
      o21 = true;
    }
    //Casilla 2-2
    if (mouseX>width/3 && mouseX<width*2/3 && mouseY>height/3 && mouseY<height*2/3) {
      ellipse(width/2, height/2, (width/3.5)-5, (height/3.5)-5);
      o22 = true;
    }
    //Casilla 2-3
    if (mouseX<width/3 && mouseY>height/3 && mouseY<height*2/3) {
      ellipse(width/6, height/2, (width/3.5)-5, (height/3.5)-5);
      o23 = true;
    }
    //Casilla 3-1
    if (mouseX<width/3 && mouseY>height*2/3) {
      ellipse(width/6, height-height/6, (width/3.5)-5, (height/3.5)-5);
      o31 = true;
    }
    //Casilla 3-2
    if (mouseX>width/3 && mouseX<width*2/3 && mouseY>height*2/3) {
      ellipse(width/2, height-height/6, (width/3.5)-5, (height/3.5)-5);
      o32 = true;
    }
    //Casilla 3-3
    if (mouseX>width*2/3 && mouseY>height*2/3) {
      ellipse(width-width/6, height-height/6, (width/3.5)-5, (height/3.5)-5);
      o33 = true;
    }
  }
  
  //Para evaluar si alguien gana
  //1er horizontal
  if((x11 == true && x12 == true && x13 == true) || (o11 == true && o12 == true && o13 == true)){
    stroke(#342A24);  
    strokeWeight(5);
    line(0, height/6, width, height/6);
    fill(255);
    textSize(70);
    text("ganaste", 20, 170);
  } 
  //2da horizontal
  else if((x21 == true && x22 == true && x23 == true) || (o21 == true && o22 == true && o23 == true)){
    stroke(#342A24);  
    strokeWeight(5);
    line(0, height/2, width, height/2);
    fill(255);
    textSize(70);
    text("ganaste", 20, 170);
  } 
  //3ra horizontal
  else if((x31 == true && x32 == true && x33 == true) || (o31 == true && o32 == true && o33 == true)){
    stroke(#342A24);  
    strokeWeight(5);
    line(0, height-height/6, width, height-height/6);
    fill(255);
    textSize(70);
    text("ganaste", 20, 170);
  } 
  //1er vertical
  else if ((x11 == true && x21 == true && x31 == true) || (o11 == true && o23 == true && o31 == true)){
    stroke(#342A24);  
    strokeWeight(5);
    line(width/6, 0, width/6, height);
    fill(255);
    textSize(70);
    text("ganaste", 20, 170);
  }
  //2da vertical
  else if ((x12 == true && x22 == true && x32 == true) || (o12 == true && o22 == true && o32 == true)){
    stroke(#342A24);  
    strokeWeight(5);
    line(width/2, 0, width/2, height);
    fill(255);
    textSize(70);
    text("ganaste", 20, 170);
  }
  //3ra vertical
  else if ((x13 == true && x23 == true && x33 == true) || (o13 == true && o21 == true && o33 == true)){
    stroke(#342A24);
    strokeWeight(5);
    line(width-width/6, 0, width-width/6, height);
    fill(255);
    textSize(70);
    text("ganaste", 20, 170);
  }
  //1ra diagonal
  else if ((x13 == true && x22 == true && x31 == true) || (o13 == true && o22 == true && o31 == true)){
    stroke(#342A24);
    strokeWeight(5);
    line(width, 0, 0, height);
    fill(255);
    textSize(70);
    text("ganaste", 20, 170);
  }
  //2da diagonal
  else if ((x11 == true && x22 == true && x33 == true) || (o11 == true && o22 == true && o33 == true)){
    stroke(#342A24);
    strokeWeight(5);
    line(0, 0, height, width);
    fill(255);
    textSize(70);
    text("ganaste", 20, 170);
  }}
  
  if (keyPressed) {
  if (key == 'n' || key == 'N')
 background(0);
 x11=false;
 x12=false;
 x13=false;
 
 x21=false;
 x22=false;
 x23=false;

 x31=false;
 x32=false;
 x33=false;

 o11=false;
 o12=false;
 o13=false;

 o21=false;
 o22=false;
 o23=false;

 o31=false;
 o32=false;
 o33=false;
 
  return;
  }
}
