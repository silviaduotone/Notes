# Icon Font

## Basics
- load svg
- name the legatures
- download the JSON and zip folder
- unzip the folder and keep the style and the font
- put them into `project/resources/icons/font|1_1`
- use : `<i class icon>`

check in the preferences the class prefix!!
from sass if yu moved the assets folder up, relink it correctly

## load them in the project folder

- copy the content of **fonts** eg: icons.eot, icons.svg etc and replace them wit the previous one
- don't replace thouth the style.scss and variables.scss!! simply open the most current files and copy the latest icons style

	    .icon-compare {
	    	&::before {
	    		content: $icon-compare;
	    	}
	    }
	and
	
	    $icon-compare: '\e935';

- in the local host page that you are working on, open the **inspector** and go to the **network** tab
- check disable cache and reload

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTM4MTUxMDM2NywyMDI2OTQzMTgzLDE0MT
AwMzkxOCwyMTk3ODg0MV19
-->