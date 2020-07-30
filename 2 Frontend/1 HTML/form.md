# Form



always use form, section, label and input

pay attention to use type= email etc to enable mobile shortcuts

use input type number just on data that needs increments, age instead of telefon number.

use button to submit, not other div styled

the button submit should be descriptive "sign in"

once you submit something, make the button disabled, to not send the info 2 times

don't ask email two times, use normal mail confirmation

use label correctly with for, and id. this creates right focus and accessible

warn for invalid inputs, by styling the :invalid 

use inpt attributes such as name=email to allow autocompletion (if you need another input but similar you can say name="new-passwerd"). 

input type=password makes the asterisks and allows suggestion for strong passwords.

make sure to add button to show password to see the text they entered (JS), as well as a button for forgot password. 

​	you can create a function to toggle passowrd by changing the input-type from password to text. add the aria description to alert that the password is being shown for blind people.

add aria-described to describe the form to blind people.

leave sign in button on mobile above the keyboards

validate data before submitting

do you even need a form? give alternative to sign up with phone, create incentives to sign up, make passowrd reset easy, kep branding consistent for trust, link to terms and policies!