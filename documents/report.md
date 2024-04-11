# Introduction
This report will document the process of implementing an animated version of the “poster 1” about climate action for children. We’ve been using CSS and SVG animations, as well as CSS and SVGs drawings, to modify and animate the existing SVGs to make it engaging and fun for kids.

# Implementation
We started our process by creating the layout, and dividing different tasks between us. Our method to animate SVG was mainly to copy the paths of each element directly from Adobe Illustrator, and put it in CodePen to test animations in isolation. This was helpful, due to some of them having many paths and groups, as well as a lot of trying and failing to make animations that would fit with our vision. We mainly put SVGs online in the HTML to animate them for more fine control, exceptions being the sun and earth with its thinking bubble. While it was not the most optimal thing to use divs to make sure they could rotate and be viewed properly, we at least wanted to make an effort to make the animations we wanted. 

Generally, we didn’t do much optimization of SVGs. In our case, the tools didn’t change the bytes a particular amount, especially when the file type is already small in size, and that sometimes they would change the original look of the SVG by removing too many anchor points. We did however group certain paths together to target a certain section of the SVG to animate, e.g. base of the cloud or individual wings of the money bag. 

To maintain the aspect ratio, we ended up using position ‘absolute’ and ‘relative’ to center items within a poster with a defined pixel width and height. As a result, the poster keeps the aspect ratio, but sadly, it has a horizontal scroll when it gets below the defined width. In hindsight, we should have used more responsive units like vw, wh and percentage, and find a better strategy when positioning. Although we made some mistakes, we wanted to make a similar looking poster by being specific with pixels and using e.g. character width on text to make it break in a similar way as the original poster design.

# SVGs
## CSS animation 
### Greenhouse gasses - animations and modifications to SVG
We have used Adobe Illustrator to modify some of the pre-existing SVG’s in the poster, in  order to solve some glaring issues with regards to their paths. Throughout the process of implementing the SVGs we noticed some strange behavior, where an SVG would look completely different from how they looked in the .ai file in Illustrator when inserted into the HTML document. What we noticed was that some paths would “glitch” and as a result they would produce new paths.

While at first glance this unexpected change isn’t too problematic in terms of aesthetics, 
it caused some issues where the trailing paths would limit our possibilities concerning animation of the “body” of these gas-clouds/particles. As shown in the final design we wanted the bodies of these to have a gas-like appearance, meaning it would move around and expand and shrink. However we didn’t want the face of each cloud to entirely disconnect from its body, therefore we modified the paths by selecting them in Illustrator and smoothing the paths (Object -> Path -> Smooth). This way the trailing paths from the eyes wouldn’t “break out of” the outline of the body. We had similar issues with a number of other SVG’s from the poster, so we’ve boiled the examples down to this singular element from the poster.

With regards to animating the greenhouse gasses in the poster, we have made it so that they move around to signify that they are gasses. We also made the outlines of the SVGs rotate around and changed the scaling of the body of each “particle” to add to this effect.
In order to achieve this behavior we have implemented them using <svg> and then given the respective <path>s classes or ids so we could select and style them using CSS.
We’ve used @keyframes along with {transform: scale()} and {transform: rotate()} to make the body of each particle/gas-cloud move around in a “gassy” fashion. 
We bound the animations to their respective HTML element using the shorthand property “animation” along with the values ease-in-out, infinite and alternate, to smoothen the animation and make it run indefinitely.

### Money Bag
In our design the thing we named “money-bag” flaps its wings and floats up and down,
to make it seem like it’s flying. In similar fashion to the greenhouse gas animations, we used the animation shorthand property along with ease-in-out, infinite and alternate to make the transitions between each iteration of the animation as smooth as possible.
Here we used {transform: translate()} to create the three-dimensional illusion of the wings flapping, and {transform: translateY()} to make it float up and down along the Y-axis.

### Sun
The principle of this animation is the same as the money-bag’s, where we select an element within the SVG to behave a certain way, while it moves along the Y-axis. In this case the sun with its rays of light moves up and down, while the rays of sunlight spin around the body of the sun indefinitely. To have certain elements of the poster move around/up and down is a recurring theme in the design we have implemented. This is partly due to the fact that the real-life objects/things they represent float around in nature, for example the sun and earth are objects that move around in space, and clouds move around in the skies. 
However it is also a conscious decision, because we believe these types of visuals are more appealing to children, as opposed to static visual elements.

### Network illustration
The poster contains an illustration of how the internet and media we use every day depends on electrical power to function. This gave us the idea to give the lines connecting the different elements an animation signifying electricity running through it, as well as giving some life to aforementioned elements. To achieve this effect we selected the <path>s attached to the “big-network” SVG we wanted to manipulate and declared CSS rules to them. 

We used @keystrokes with {fill} attribute alongside {animation: *insertName* forwards infinite} to make the lines connecting to the buildings and media-devices etc. change to a bright cyan color, representing electricity running through them. To add to this effect the windows on the buildings turn to a yellow color as well, as if the rooms of the buildings light up. We also used @keyframes {x% {opacity: x; transform: translateY(x)} to animate the wi-fi signal above each building to “grow” upwards.

### Cloud
When animating the rainy cloud, we used @keyframes because we’re most comfortable and familiar with how it works and the syntax of it. Besides, the CSS rule is similar to the ones declared in many other animations so we found it most efficient to do it in a similar fashion, as we only needed to copy-paste an earlier @keyframe and change its animation name, properties and values to taste. 
We used @keyframe {x%{transform: translateY(x); opacity: x;} to achieve the resulting animation, where the rain falls like tears from the eyes of the cloud and the change of opacity adds some smoothness to the animation as it iterates. 


### Flame animation
We used @keyframes {x% {transform: rotate(xdeg) translateX(x) scale(x)}} combined with manipulating path data ( {d: path();} ) to make the flame “flutter” like a flame in real-life.
Notably we set the time on the animation property to 0.8s, to make it more erratic. 

### Earth and thought bubble
We used @keyframes {x% {transform: rotate(xdeg);} to make the planet spin around, and the thought bubbles coming from it uses @keyframes {x%{opacity: x;}} to sequentially display the thought bubble before it reiterates.

### Wave animation
By manipulating the path data, like we did on the flame animation, we could make the dark blue svg in the middle wave similar to a river. We wished to animate one of the curves, and we felt this was the perfect animation concept for our poster. By manipulating the waves of the svg in Illustrator, we made two other versions, copied the path, and defined it on keyframe  50% and 100% respectively. Combined with ‘alternate’, it started flowing like a river with just a few keyframes. We also added three <circle> elements, simulating bubbles, that went up the Y-axis from the curve, and “popped” by reducing the radius of the circle to 0 in another animation. We found out this was possible by seeing a CodePen where they put the radius inside a custom variable (--var) within each element, as just targeting the radius didn’t seem possible. That CodePen also had a blur filter by adding <feGaussianBlur> among other things, and we thought that would be fitting for our bubbles as well.

## SMIL animations
On many of our animations we have utilized CSS keyframes to animate SVGs, but we’ve also used SMIL (Synchronized Multimedia Integration Language) for animation. We utilized SMIL path animation (<animationMotion>), transform animation (<animateTransform>) and animation (<animate>) at least once. 

### SMIL path 
The four pointed star, which we made with the <polygon> element by specifying eight coordinates, follows the path of a svg based on the pink background curve, obtained using “Offset path” in Illustrator, by linking the star svg with the path id of that curve. We made the fill ‘yellow’ with a thick black line to make it blend with the rest of the poster. Preferably, we would have created the svg curve as a polyline, but we didn’t understand how to do this. The other path animation we created was on the two wriggly arrows pointing to the table and the green gas elements. It follows a small straight path, and by putting the duration at 1s, we’re able to get a back-and-forth like pointed animation that we wanted to enhance the fun feeling of the website.

### SMIL transform
We used SMIL transform on the base of the cloud svg to increase the scale from 1 to 1.1. We found it fitting as it gave the feeling of a dynamic cloud that expands and contracts. However, we only did this once as we felt transforming through CSS keyframes was easier and gave us more control of how we wanted the animation to show.

### SMIL animate
When learning about what was possible with SVG animations, the idea of changing one color from another sounded like a type of animation that would enhance the visual appeal of the poster. We targeted the ‘fill’ attribute of the two wiggly arrows, that also used path animation, to make it change color from yellow to green.

# Drawing
We “drew” two elements using CSS drawing: the table about energy, and the two white lines in the footer. This was done using ‘::before’ and ‘::after’’, setting the content to empty, and using positioning absolute. The white lines in the footer were pretty straight forward, but when it came to the table we had three lines due to the horizontal line being slightly bent on the right side. This was possible by rotating using ‘transform’, and matching the lines to make it look seamless. When it came to making SVGs, we used the <circle> element to create three bubbles, and a four-pointed star using the <polygon> one.