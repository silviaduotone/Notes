# Alignment 
## text-align
text-align mozilla
serve una classe speciale


## Clearfix

quando usi float left and right crei uno strano flow. 
per quello è importante dare una classe clearfix al parent
cosi che fa come borderbox. calcola tutte le trasformazioni e rimette l'oggetto nel suo flow.

## clear

clear  =  none|left|right|all 
Specifies **where the next line should appear** in a visual browser after the line break caused by this element. This attribute takes into account floating objects (images, tables, etc.). Possible values:

-   none:  The next line will begin normally. This is the default value.
-   left:  The next line will begin at nearest line below any floating objects on the left-hand margin.
-   right:  The next line will begin at nearest line below any floating objects on the right-hand margin.
-   all:  The next line will begin at nearest line below any floating objects on either margin.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTE2NDg4MzY5NSwxMDA3OTM0NzY3LC0xMj
k1NTU4NTE5XX0=
-->

# modern layouts

### super centred

display:grid;

place-items:center;



### pancake layout

display: flex

flex-wrap: wrap

justify-content: center;



items:

flex: 1 1 150px; (with strech)

flex: 0 1 150px; without strech (the third is the base width)



### sidebar

display: grid;

grid-template-columns: min-max(150px, 25%) 1fr;



### header body footer 

display: grid;

grid-template-rows: auto 1fr auto;



### RAM (repeat, auto, minmax)

display: grid;

grid-gap: 1rem;

grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));



### clamping width depending on character! (not in safari)



width: clamp(23ch, 50%, 46ch);

display:flex;



### aspect-ration (still work in progrss)



aspect-ratio: width/height

