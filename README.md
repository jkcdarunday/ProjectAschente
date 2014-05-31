ProjectAschente
===============

An open-source HTML5-based visual novel engine project.

The presentation page will have two DOM Objects.
First is an HTML5 Canvas that will be responsible for the render of images.
On top of it is an HTML Div that will contain text and handle user interaction.
An object of each class will be instantiated and exposed to what will be a main script like Ren'py does.

The following is the currently proposed hierarchy of classes for the Engine:

*    **Renderer** - Handles the rendering of a Scene to an HTML5 Canvas Object
*    **Scene** - Contains a list of Image and Text instances along with the corresponding Audio.
*    **Character** - Pretty much an array of images of the different emotions of a character with an included name
*    **Image** - Contains a link to an image and its position in a scene
*    **Audio** - Audio support
*    **Video** - Video support
    
P.S. Title is still to be decided upon.

Planned functions to be implemented:
```
Image(<URL>, <XPosition>, <YPosition>, <Origin:Centered/TopLeft>)
Image(<URL>, <Left/Center/Right>, <Origin:Centered/TopLeft>)
Image.moveTo(<Type>, <TargetX>, <TargetY>)
Image.moveTo(<Type>, <Left/Center/Right>)
Image.move(<Type>, <XInitial>, <YInitial>, <XTarget>, <YTarget>)
Image.move(<Type>, <Initial:Left/Center/Right>, <Target:Left/Center/Right>)
Image.setOpacity(<Value>, <Type>)
Image.setOpacity(<Value>)
Character(<Name>)
Character.setEnabled(<Boolean>)
Character.addEmotion(<Emotion>, <Image>)
Character.deleteEmotion(<Emotion>, <Image>)
Character.replaceEmotion(<Emotion>, <Image>)
Character.say(<Text>)
Character.getImage()
Renderer(<2dContext>, <Div Element>)
Renderer.setScene(<Scene>)
Renderer.update()
Scene()
Scene.setBackgroundTransition(<URL>)
Scene.setBackground(<Image>)
Scene.setBackground(<URL>)
Scene.setFrame(<URL>)
Scene.setFrame(<Image>)
Audio(<URL>)
Audio.play(<Looped:Boolean>)
Audio.pause()
Video(<URL>)
Video.play()
Video.pause()
```

Planned script flow:
```
var canvas = document.getElementById('canvas');
var html = document.getElementById('html');
var r = new Renderer(canvas, html);
r.Configure({
        text-transition: "ease",
        text-font: "Open Sans",
        text-frame: "frame.png",
        text-padding: "10px",
        choice-padding: "3px",
        choice-frame: "cframe.png"
    });

r['k'] = r.Character("Keith", {color:"black"});
r['y'] = r.Character("Random Person", {color:"black"});

k.say("Well hello there");
r.say("Ohai!");

r.Menu(r,
    {
        "Destroy Earth":function(r){
            r['k'].say("What on earth!");
            r['k'].say("Why would you destroy earth?");
        },
        "Destroy the Sun":function(r){
            r['k'].say("What on earth!");
            r['k'].say("Why would you destroy sun?");
        }
    });

```