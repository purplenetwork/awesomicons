### EXAMPLE

Consider the following file system after __*AwesomIcons*__ installation:

    package.json
    node_modules/
    app/
     |
     |-- index.html
     |
     |-- images/
     |    |
     |    '-- icons/
     |         |
     |         '-- weather.svg
     |
     '-- styles/
          |
          |-- main.scss
          |
          '-- modules/
               |
               '-- _icons.scss
                
and the content of __weather.svg__ below:

    <svg version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
    	 width="24px" height="22.2px" viewBox="0 0 24 22.2" style="enable-background:new 0 0 24 22.2;" xml:space="preserve">
    	<g id="sun">
    		<path fill="{{__AI-COLOR-1__}}" d="M12,8c0,0.4-0.1,0.8-0.2,1.2c-2,0.4-3.8,1.2-5.3,2.5C5,11.1,4,9.7,4,8c0-2.2,1.8-4,4-4S12,5.8,12,8z"/>
    		<g fill="{{__AI-COLOR-2__}}">
    			<path d="M3.8,5.2L1.6,3.1l1.4-1.4l2.2,2.2C4.7,4.2,4.2,4.7,3.8,5.2z"/>
    			<path d="M16,9V7h-3.1C13,7.3,13,7.7,13,8s0,0.7-0.1,1H16z"/>
    			<path d="M12.2,5.2L14.4,3L13,1.6l-2.2,2.2C11.3,4.2,11.8,4.7,12.2,5.2z"/>
    			<path d="M9,3.1V0H7v3.1C7.3,3,7.7,3,8,3S8.7,3,9,3.1z"/>
    			<path d="M3.8,10.8L1.6,13l1.4,1.4l2.2-2.2C4.7,11.8,4.2,11.3,3.8,10.8z"/>
    			<path d="M3,8c0-0.3,0-0.7,0.1-1H0v2h3.1C3,8.7,3,8.3,3,8z"/>
    		</g>
    	</g>
    	<g id="rainbow">
    		<path fill="{{__AI-COLOR-3__}}" d="M14,13.2c-4.1,0-8,2.9-8,9h1c0-5.4,3.4-8,7-8c3.7,0,7,2.6,7,8h1C22,16.1,18,13.2,14,13.2z"/>
    		<path fill="{{__AI-COLOR-4__}}" d="M14,11.2c-5,0-10,3.7-10,11h1c0-6.7,4.5-10,9-10s9,3.3,9,10h1C24,14.8,19,11.2,14,11.2z"/>
    		<path fill="{{__AI-COLOR-5__}}" d="M14,15.2c-3.2,0-6,2.2-6,7h1c0-4.1,2.3-6,5-6c2.6,0,5,1.7,5,6h1C20,17.4,17.1,15.2,14,15.2z"/>
    	</g>
    </svg>

As you can see, each *fill* attribute contains a placeholder as value. In this example, we are using the multi-color mode, so the icon will be colored with different color layers.

> __N.B.:__ If you set your *SVGs* for multi-color mode, you can also use a single color to paint your icon as all placeholders will be replaced by the same value if only one color is provided.

Now, by running the following command:

    npm explore awesomicons -- npm run awesomicons app/images/icons app/styles/modules/_icons.scss
    
the content of __\_icons.scss__ will look as follows:

```scss
$awesomicons: (
    'weather': '%3Csvg%20version=%221.1%22%20xmlns=%22http://www.w3.org/2000/svg%22%20xmlns:xlink=%22http://www.w3.org/1999/xlink%22%20x=%220px%22%20y=%220px%22%0A%09%20width=%2224px%22%20height=%2222.2px%22%20viewBox=%220%200%2024%2022.2%22%20style=%22enable-background:new%200%200%2024%2022.2;%22%20xml:space=%22preserve%22%3E%0A%09%3Cg%20id=%22sun%22%3E%0A%09%09%3Cpath%20fill=%22%7B%7B__AI-COLOR-1%7D%7D%22%20d=%22M12,8c0,0.4-0.1,0.8-0.2,1.2c-2,0.4-3.8,1.2-5.3,2.5C5,11.1,4,9.7,4,8c0-2.2,1.8-4,4-4S12,5.8,12,8z%22/%3E%0A%09%09%3Cg%20fill=%22%7B%7B__AI-COLOR-2%7D%7D%22%3E%0A%09%09%09%3Cpath%20d=%22M3.8,5.2L1.6,3.1l1.4-1.4l2.2,2.2C4.7,4.2,4.2,4.7,3.8,5.2z%22/%3E%0A%09%09%09%3Cpath%20d=%22M16,9V7h-3.1C13,7.3,13,7.7,13,8s0,0.7-0.1,1H16z%22/%3E%0A%09%09%09%3Cpath%20d=%22M12.2,5.2L14.4,3L13,1.6l-2.2,2.2C11.3,4.2,11.8,4.7,12.2,5.2z%22/%3E%0A%09%09%09%3Cpath%20d=%22M9,3.1V0H7v3.1C7.3,3,7.7,3,8,3S8.7,3,9,3.1z%22/%3E%0A%09%09%09%3Cpath%20d=%22M3.8,10.8L1.6,13l1.4,1.4l2.2-2.2C4.7,11.8,4.2,11.3,3.8,10.8z%22/%3E%0A%09%09%09%3Cpath%20d=%22M3,8c0-0.3,0-0.7,0.1-1H0v2h3.1C3,8.7,3,8.3,3,8z%22/%3E%0A%09%09%3C/g%3E%0A%09%3C/g%3E%0A%09%3Cg%20id=%22rainbow%22%3E%0A%09%09%3Cpath%20fill=%22%7B%7B__AI-COLOR-3%7D%7D%22%20d=%22M14,13.2c-4.1,0-8,2.9-8,9h1c0-5.4,3.4-8,7-8c3.7,0,7,2.6,7,8h1C22,16.1,18,13.2,14,13.2z%22/%3E%0A%09%09%3Cpath%20fill=%22%7B%7B__AI-COLOR-4%7D%7D%22%20d=%22M14,11.2c-5,0-10,3.7-10,11h1c0-6.7,4.5-10,9-10s9,3.3,9,10h1C24,14.8,19,11.2,14,11.2z%22/%3E%0A%09%09%3Cpath%20fill=%22%7B%7B__AI-COLOR-5%7D%7D%22%20d=%22M14,15.2c-3.2,0-6,2.2-6,7h1c0-4.1,2.3-6,5-6c2.6,0,5,1.7,5,6h1C20,17.4,17.1,15.2,14,15.2z%22/%3E%0A%09%3C/g%3E%0A%3C/svg%3E%0A',
);
```

Also, take a look at __main.scss__ file, where __*AwesomIcons*__'s *SCSS* library and __\_icons.scss__ are included along with other dependencies:
    
```scss
@import '../../node_modules/awesomicons/lib/awesomicons';
@import './modules/icons';
[...]
```
    
Since configuration is complete, we just have to create an *HTML* icon element like this:

```html
<i class="your-icon-class"></i>
```
 
and stylize it as follows:

```scss
.your-icon-class {
    @include awesomicon(rainbow, #ff9900 #ffcc00 #cc6633 #cccc33 #3399cc);
}
```

Enjoy your icons after *SASS* compiling!

    
### TIPS AND TRICKS

In addition to icon's *[name]* and *[colors]*, the __awesomicon()__ mixin also accepts a third parameter to improve your icons: an options map with the following properties:
    
* *[width]*: the icon block's width (default: 1em)
* *[height]*: the icon block's height (default: 1em)
* *[padding]*: the icon block's padding (default: 0)
* *[position]*: the icon's position (default: 50% 50%)
* *[background]*: the icon block's background-color (default: transparent)
* *[border]*: the icon block's border (default: none)
* *[radius]*: the icon block's border-radius (default: none)

For example, you can combine *background* and *radius* to get colored icon blocks with different shapes (e.g. square/circle) or you may want to use *position* to adjust icon's alignment to fit the best with your context. Here, an hint:

```scss
.your-icon-class--circle {
  @include awesomicon(rainbow, #ffffff, (padding: 4px, background: #3399cc, radius: 50%));
}
```

You can also build a simple framework to have a *CSS* class-based icons handling, like the following:
    
```scss
$colors: (
    'orange': #ff9900,
    'yellow': #ffcc00,
    'red': #cc6633,
    'green': #cccc33,
    'blue': #3399cc
);

@each $icon-name, $icon-code in $awesomicons {
    .icon--#{$icon-name} {
        @each $color-name, $color-value in $colors {
             &.icon--#{$color-name} {
                @include awesomicon($icon-name, $color-value);
            }
        }
    }
}
```

and use it as below:

```html
<i class="icon--weather icon--blue"></i>
```