# Sixfold geometry snowflake in p5

you use scale and move the origin to the center and rotate it by the angle to create this flip effect!


    let symmetry = 6;
    let angle = 360/symmetry;
    
    let saveButton;
    let clearButton;


​    
​    
    function setup() {
      createCanvas(800, 800);
      background(0);
      angleMode(DEGREES);
      translate(width/2,height/2);
      
      saveButton = createButton('save');
      saveButton.mousePressed(saveSnowflake);
      clearButton = createButton('clear');
      clearButton.mousePressed(clearCanvas);
    }
    
    function saveSnowflake(){
      save('snowflake.png');
    }
    
    function clearCanvas(){
      background(0);
    }


​    
    function draw(){
      
      translate(width/2,height/2);
      
      let mx = mouseX - width/2;
      let my = mouseY - height/2;
      
      let pmx = pmouseX - width/2;
      let pmy = pmouseY - height/2;


​      
      if (mouseIsPressed){
      stroke(255, 100);
        let angle = 360/symmetry;
        for (let i = 0; i<symmetry; i++) {
          
          rotate(angle);
          let d = dist(mx, my, pmx, pmy);
          let sw = map(d, 0, 10, 10, 1);
          strokeWeight(sw);


​    
          line(mx, my, pmx, pmy);
    
          push();
          scale(-1,1);
          line(mx, my, pmx, pmy);
          pop();
        }    
      }
    }