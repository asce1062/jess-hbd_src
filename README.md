# jess-hbd_src
This is an example of an application made with MASM32.

![jess-hbd_src](https://github.com/asce1062/jess-hbd_src/raw/master/jess-hbd_src.PNG)

[![jess-hbd_src](http://img.youtube.com/vi/Hhkeni5XBH0/0.jpg)](https://youtu.be/Hhkeni5XBH0)
 
<pre>
        _____  .__                     .___                              
       /  _  \ |  |   ____ ___  ___    |   | _____   _____   ___________ 
      /  /_\  \|  | _/ __ \\  \/  /    |   |/     \ /     \_/ __ \_  __ \
     /    |    \  |_\  ___/ >    <     |   |  Y Y  \  Y Y  \  ___/|  | \/
     \____|__  /____/\___  >__/\_ \ /\ |___|__|_|  /__|_|  /\___  >__|   
             \/          \/      \/ \/           \/      \/     \/       
</pre>

<pre>
      █████╗ ██╗     ███████╗██╗  ██╗   ██╗███╗   ███╗███╗   ███╗███████╗██████╗ 
     ██╔══██╗██║     ██╔════╝╚██╗██╔╝   ██║████╗ ████║████╗ ████║██╔════╝██╔══██╗
     ███████║██║     █████╗   ╚███╔╝    ██║██╔████╔██║██╔████╔██║█████╗  ██████╔╝
     ██╔══██║██║     ██╔══╝   ██╔██╗    ██║██║╚██╔╝██║██║╚██╔╝██║██╔══╝  ██╔══██╗
     ██║  ██║███████╗███████╗██╔╝ ██╗██╗██║██║ ╚═╝ ██║██║ ╚═╝ ██║███████╗██║  ██║
     ╚═╝  ╚═╝╚══════╝╚══════╝╚═╝  ╚═╝╚═╝╚═╝╚═╝     ╚═╝╚═╝     ╚═╝╚══════╝╚═╝  ╚═╝
</pre>

<pre>
     .______  .___    ._______ ____   ____.___ ._____.___ ._____.___ ._______.______  
     :      \ |   |   : .____/ \   \_/   /: __|:         |:         |: .____/: __   \ 
     |   .   ||   |   | : _/\   \___ ___/ | : ||   \  /  ||   \  /  || : _/\ |  \____|
     |   :   ||   |/\ |   /  \  /   _   \ |   ||   |\/   ||   |\/   ||   /  \|   :  \ 
     |___|   ||   /  \|_.: __/ /___/ \___\|   ||___| |   ||___| |   ||_.: __/|   |___\
         |___||______/   :/               |___|      |___|      |___|   :/   |___|    
                                                                                 
</pre> 

# [ Info ]
---  
An example oldschool-style program written in MASM32 with several effects in it. You can type in the x/y coordinates for the logo, scroll text, etc, and you can load custom logos and fonts.
  
                       [ code ........... asce1062 ]
                       [ BMP2RAW ........ Flyke ]
                       [ bin2dbex ........ Steve Hutchesson ]
                       
## IMPORTANT

When you use a bitmap font, the order of the letters must be :

	- One line - if you have a multi-char lined font like 
	  " abcdefghij "
	  " klmnopqrst ", you must convert the font so it is like this :
	  " abcdefghijklmnopqrstuvwxyz ".
	- In ascending hex value order from 0x20
	  so : 0x20, 0x21, 0x22, 0x23.....
	  or in ASCII : " !"#$%&' "
	  this can go on as long as you like, even until 0xFFh.
	- should be 8x8 or 16x16. in theory, any size is ok, but it 
	  will look HORRIBLE

### [ Instructions ]

- Create a `256-color` BMP file. `24-bit` or `16-color` BMPs will not work
           Use a paint package (such as MS-Paint) to load your logo/font
           and just save as `256` color bitmap. Do this to all your fonts and
           your logos which you want to use in the application.
- Drag and drop the bmp onto "`256BMP2RAW.exe`". You should see a
           console window pop up and convert the stuff into a `.pallete`
           and `.picture` file. In Windows Vista and 7, the files will be dropped
           into the directory containing the program. However, if you're
           running XP, you will need to go to
           `C:\documents and settings\\`
           and the files should be called `.picture` and `.pallete`.
- Load "`bin2dbex.exe`" and load the `.pallete` and the `.picture` file for it. 
           You will need to copy the `compacted DB DECIMAL notaion` of each file i.e font file
           and logos for both the `.pallete` and the .picture files and create `font.asm` 
           and `logo.asm` containing the `compacted DB DECIMAL notation`. Refer to
           `DATA/font.asm` for more clarification. 
- Once you have loaded the right stuff into your IDE of choice (I use `WINASM`),
           Enter in the right `X` and `Y` positions for the related fields.
           Remember that the screen is `640x480` so if your logo is.. say
           `100 px high`, entering the `Y position` as `600` will crash the
           application `(600+100)`=`700` = `off the screen`
- If you have selected the scroller/page text options, please edit the size and
           location of to match your taste.
- PRESS `MAKE` -> `GO ALL!` or `shift+f8` .

  That's all for now :)
  
  have fun with the program!
  
  #### PS: The music contained here i.e `DATA/song.xm` is one of my compositions, licensed under Creative Commons with Attribution. Please credit me if you use it for any non-commercial purposes. Else for commercial purposes, don't hesitate to contact me.
  
 /asce1062 