# Vector

[https://natureofcode.com/book/chapter-1-vectors/](https://natureofcode.com/book/chapter-1-vectors/)

### what are vectors
a vector has **magnitude**  and **direction**

the magniture is the length or size. long Sto arrivando!ow or short arrow
while the direction is the angle relative to some axis.

a vector can be separated into a x and y component.as a pytagoran formula.

    float x, y;
    x = x +xSpeed;
    y = y + ySpeed;

This kind of code is complex and you will repete many times x and y, this is why we use Vectors: which in processing are initiated like this: 

    Pvector position;

###  Pvector class

you define the object and then you instantiate the vector

    Pvector position;
    // float x, y;
    PVector location;
    
    //x = width/2;
    //y= height/2;
    location = new PVector(width/2,height/2);

to access the single values you do

    location.x 

if an object has a position, how it will change over time is velocity
How to add two vectors toghether?
the + operator is reserved only for primitive types


     //x = x + xspeed;
     //y = y + yspeed;
     
     // not like this!
     location = location + velocity;
     // but like this
    location = location.add(velocity);


  you should use functions **add()** **sub()** and **muH();**





# Vector Math

16min, 11 min  14min 10 min = 51 minuti, un ora!

### list of math functions for processing
[https://processing.org/reference/PVector.html](https://processing.org/reference/PVector.html)

## multiplication, scale
mult(Diu) "scale

you multiply by a scale of a scalar.
what changes is the lenght .

## magnitude "mag"  .mag()

annotation of a simple vector
$$
\vec{v} 
$$
this is the annotation of a magnitude, its length
$$
\| \mathbf{v} \|
$$


## .normalize()

a normal vector has a lenght of 1
but keeps the direction! it is divided by its own lenght.

in a practical sense, is when you visually want to only care about hte direction but not the lenght

    v.normalize();

a function that does that and also multiplies to a certain value is

    .setMag()



# Acceleration

    location.add(velocity);
    velocity.add(acceleration);

we want velocity to grow over time.

take care that the units are pixel, so take very small values!

when acceleration changes with time is more interesting

## non constant acceleration

Vector has a random direction!

    acceleration = PVector.random2D();
    velocity.limit(5); 

### the function .limit(int );

very useful to cap a number and not have the accelleration fuck up everything.

## acceleration towards mouse

to find the vector from the mouse position and the current position you want to use sottrazione.

the   mousepos = new PVector(mouseX,mouseY); has to be in the update function since you modify that at each frame!!

### example code

    void update(){
      
        //get current pos
        mousepos = new PVector(mouseX,mouseY);
    
      // fin the vector from center to mouse
        mousepos.sub(location);
        
        // slow the acceleratino to get there
        mousepos.setMag(0.1);
        
        acceleration = mousepos;
        
        velocity = velocity.add(acceleration);
        velocity.limit(5);
        location = location.add(velocity);
          
      }





# Random Walker, Intro


### code setup x java

	// to initiat an object start with the name of the class
	Walker w;
	
	void setup(){
	  size(800,600);
	  w = new Walker();
	  background(255);
	}
	
	void draw(){
	w.step();
	w.render();
	}

### Class of the walker, 
object oriented
note that void is like function and methods

        class Walker {
      int x,y;
      
      Walker(){
       x = width/2;
       y = height/2;
      }
    
    void render(){
    stroke(0);
    point(x,y);
    }
    
    void step(){
    
    // adding probability
      float choice = random(1);
    
      if (choice < 0.5){
        x++;
      } else if (choice < 0.6){
        x--;
      } else if
      (choice < 0.9){
        y++;
      }
      else{
      y--;
      }
    
      x = constrain(x,0,width-1);
      y = constrain(y,0,height-1);
    }
    }

## probability

probabilità è una media della distribuzione di numeri.
custom distribution of random numbers

se hai un numero da 0 a 1, puoi dire che 50 % è da 0 a 0.5
metà delle possibilità
if random <= 0.5
if random > 0.5 and < 0.8  è 30 %

## gaussian distribution of random numbers

how can you control randomness with more harmony and control.

in nature there is a **bell curve** in the distribution of randomnes
there are more animal at the medium spot, than at the extreme edges

to use randomness in java you can import the library **util random.j**

    import java.util.Random;

example of code, note : define variables, in setup generate random object, call it in draw();

    import java.util.Random;
    
    Random generator;
    
    void setup(){
      size(800,600);
      
      generator = new Random();
    }
    
    void draw() {
      background(150);
      
      // cast the double as a float with parentheris, processing wants that
      float h = (float) generator.nextGaussian();
      
      fill(0);
      ellipse(width/2, height/2,h,h);
     
    }


### standard deviation

how much it goes away from the mean.

in the object you didn't specify the range.
the smaller the number, the smaller the deviation from the mean. 

    h è un numero da 0 a 1
    h *= standardDeviation;
    h = h+mean; 

 se calcoliamo the l'altezza base è 1.80m. random h saranno i centimetri in piu o in meno. e quanto sono grandi e quanto recente è l'addizione dipendera dalla standard deviation.


### custom distribution

#### bucket approach
usando degli array si puo usare un approccio alla bucket: a dipendenza di quanti elementi si ripetono nel bucket, nel nostro caso nell array, si crea una custom probabilità che non dipende da un solo numero e una media legata ad esso. ma da diversi poli. questa logica è legata all'evoluzione.

#### probably distribution

picking 2 random numbers (0,100)
if random2 < random1 ok
else: sad
we have to create a if else that evaluates how good is the value.

se il numero è 50 per esempio, abbiamo 50% possibilità che il numero sia maggiore o minore. con 90, 10 % possibile che sia maggiore.

montecarlo()  a simulation to pick many numbers after the others like gambling

## Perlin noise

help to create a smooth natural curve.
time is going linear, a normal randomness the numbers have no connection to the others that came before or after.

perlin takes into account what's happening around it

what are the arguments of perlin noise?
we feed time.  an animation. 
so t should be something like a small value.

    float t = 0;
    t = t + 0.01;
    float x = noise(t);
    x = map(x, 0,1,0,width);

perlin noise gives values between 1 and 0.
 to map it into a different range you should use .map();