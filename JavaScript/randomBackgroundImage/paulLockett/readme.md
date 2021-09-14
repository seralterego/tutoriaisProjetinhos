# Random Background Image

:link: <<https://paul-lockett.co.uk/randombackground.htm>

> You might have noticed that the background of the pages on this site changes randomly. It is quite easy to achieve this using Javascript. In fact, I've got two separate methods for doing it, which offer slightly different functionality.

## [Method 1](./src/method01/index.html)

> In the head section of the web page, place the following code:
>
> ~~~javascript
> <script type="text/javascript">
>   function backgr(){
>     var backimg = ["img01.jpg", "img02.jpg", "img03.jpg", "img04.jpg"];
>     var randimg = Math.floor(Math.random()*4);
>     document.body.background = backimg[randimg];
>   }
> </script>
> ~~~
>
> Where "img01.jpg", etc are the urls of the images that you want to use. The only other thing you need to do is change the tag in the body to read:
>
> ~~~html
> <body onload="backgr()">
> ~~~
>
> This is the simpler of the two methods and works well in most cases.

## [Method 2](./src/method02/index.html)

> In the head section of the web page, place the following code:
>
> ~~~javascript
> <script type="text/javascript">
>   function backgr() {
>     var randimg = Math.floor(Math.random(*4));
>     if (randimg == 0) {
>       document.getElementById('bod').className="bg1";
>     } else if (randimg==1) {
>       document.getElementById('bod').className="bg2";
>     } else if (randimg==2) {
>       document.getElementById('bod').className="bg3";
>     } else if (randimg==3) {
>       document.getElementById('bod').className="bg4";
>     }
>   }
> </script>
> ~~~
>
> ~~~css
> <style type="text/css">
>   .bg1 {
>     background-image: url("img01.jpg");
>   }
>   .bg2 {
>     background-image: url("img02.jpg");
>   }
>   .bg3 {
>     background-image: url("img03.jpg");
>   }
>   .bg4 {
>     background-image: url("img04.jpg");
>   }
> </style>
> 
> Where "img01.jpg", etc are the urls of the iamges that you want to use. The only other thing you need to do is change the tag in the body to read:
> ~~~html
> <body id="bod" onload="backgr()">
> ~~~
>
> This method is a bit less succinct, but it is a bit more flexible, as the CSS section can be adjusted so that other elements of the page, such as the font, change alongside the background image. You could also put the id="bod" into a tag other than the body if you wanted the image to cover part of the page.  
