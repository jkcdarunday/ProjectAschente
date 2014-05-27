ProjectAschente
===============

An open-source HTML5-based visual novel engine project.

The following is the currently proposed hierarchy of classes for the Engine:

*    **Renderer** - Handles the rendering of a Scene to an HTML5 Canvas Object
*    **Scene** - Contains a list of Image instances
*    **Character** - Pretty much an array of images for the different emotions of each character
*    **Image** - Contains the location of an image and its position in a scene
*    **Interpreter** - Interprets VN scripts.
    
P.S. Title is still to be decided upon.
    
```
Image(<URL>, <XPosition>, <YPosition>, <Origin:Centered/TopLeft>)
Image(<URL>, <Left/Center/Right>, <Origin:Centered/TopLeft>)
Image.moveTo(<Type>, <TargetX>, <TargetY>)
Image.moveTo(<Type>, <Left/Center/Right>)
Image.move(<Type>, <XInitial>, <YInitial>, <XTarget>, <YTarget>)
Image.move(<Type>, <Initial:Left/Center/Right>, <Target:Left/Center/Right>)
Character(<Name>)
Character.addEmotion(<Emotion>, <Image>)
Character.deleteEmotion(<Emotion>, <Image>)
Character.replaceEmotion(<Emotion>, <Image>)
Character.getImage()
Renderer(<2dContext>)
Renderer.setScene(<Scene>)
Renderer.update()
```