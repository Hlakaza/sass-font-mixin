# sass_font_mixin
A mixin for embeding fonts using sass

How to use the font

Create your ``css`` as below

import this ``` _font_mixin.scss ``` to your ``style.scss ``

 
``@import 'font_mixin';``
****************************************************************
Always add  ``` @include set-font('OpenSans'); ``` at the top of your 
styles below ``` @import 'font_mixin'; ``` this builds your ``@fontface;``
depending with the number of fonts you have this will be set like below;

`````````
@include set-font('OpenSans');
@include set-font('OpenSans');
@include set-font('Roboto');
`````````
Compiled `set-font`` will look like below
````````
@font-face {
    font-family: "OpenSans";
    font-style: normal;
    font-weight: bold;
    src: url("fonts/OpenSans.eot?") format("eot"),
    url("fonts/OpenSans.woff2") format("woff2"),
    url("fonts/OpenSans.woff") format("woff"),
    url("fonts/OpenSans.ttf") format("truetype"),
    url("fonts/OpenSans.svg#OpenSans") format("svg");
}
`````````
******************************************************************************
You then include the ```use-set-font mixin``` in your class, pass the font name like `` @include use-set-font('your_font_name');``

``````````    
.header { 
    @include use-set-font('OpenSans');
}
.content { 
    @include use-set-font('Roboto');
}
.footer { 
    @include use-set-font('OpenSansBold');
}
``````````

Compiled results will be like below

``````````
.header { 
    font-family: "OpenSans";
    font-weight: normal;
    letter-spacing: 0;
}
.content { 
    font-family: "Roboto";
    font-weight: normal;
    letter-spacing: 0;
}
.footer { 
    font-family: "OpenSansBold";
    font-weight: normal;
    letter-spacing: 0;
}
``````````