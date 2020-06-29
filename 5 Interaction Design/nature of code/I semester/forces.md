# Newton's law

[https://www.youtube.com/watch?v=II1A3bBo6gM&list=PLRqwX-V7Uu6ZRrqLcQ5BkBKmBLiGD8n4O](https://www.youtube.com/watch?v=II1A3bBo6gM&list=PLRqwX-V7Uu6ZRrqLcQ5BkBKmBLiGD8n4O)

## three laws of motion

1. an object at rest stays at rest, an object in motion stays in motion. in absence of forces no force is required to keep an object moving
2. force equals mass X acceleration
3. force comes in pairs, for every actions there is a reaction force

## newton second law in processing

**force = mass * acceleration** is equal to **Acceleration = Forces/mass**

this is good, because we now know how to implement this law.

Pvector acceleration = force

but it's more complex. usually there are more than one force at time. this is called force accumulation

### force accumulation

more precisely the law refers to:
**net force = mass * acceleration**

this is why **equilibrium** exists, if the two forces cancel eachothers, the net forces is 0, thus acceleration is also 0, and the object doesn't move!

**0 = mass * acceleration.**

in processing we have then to .add(forces)
before calculating them. remembering to set the vector to 0 at every frame to not add up the velocity (unlike location that know where it was in the previous frame, acceleration is just a number, if there is a noise 4 that becomes 5, if you don't set it to zero it will equal 9 in the next frame, not 5). An easy way to do that is mutlipliying it by 0.

	void update() {
	velocity.add(acceleration);
	location.add(velocity);
	acceleration.mult(0);
	}
	
	void applyForce(Pvector force){
		acceleration.add(force)
	}
	
		if (mousePressed){
		Pvector wind = new PVector(0.5,0);
		mover.applyForce(wind);
	}


# Dealing with mass

The heavier the object, the bigger the acceleration needs to be.
bigger objects move slowly.

How do you add mass to a pixel?
add mass as a float in the init class of the mover object

float mass;

for start we can invent the units, we can say a circle has float 10,0 mass.

! note that you need the **Pvector .get()** because in object programming, the arguments are not copied, so once you modify the original vector, the next time you are going to use it, it will keep the transformation. using .get(); will create a copy f of the force, that you can modify as you please.

     void applyForce(Pvector force){
        Pvector f = force.get();
        f.div(mass);
        acceleration.add(f) 
    }


​	
### initializing arrays

    Mover[] movers;

and then initialize how many of them

       movers = new Mover[5];
      for (int i = 0; i < movers.length; i++){
        movers[i] = new Mover();
      }

you can also use an Enhanced loop:

    for(Mover m : movers){
         m.applyForce(gravity);
        
        if(mousePressed){
          m.applyForce(wind);
        }
      
    m.update();
    m.edges();
    m.display();
  }



# Formulae, Friction

1 evaluae the right side, assign to the left side.
2 understand when an element is a vector or a scalar
3 letters usually are intended to be multiplied

## Friction