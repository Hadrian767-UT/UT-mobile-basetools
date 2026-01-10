# Adding the DEBUG mode for the games that don't have DEBUG mode natively

## Attribute the DEBUG global variable

In code<br />

```
gml_Object_world_Create_0
```

After the last line, you will put:

```gml
global.debug = 0;
```

After this, let's put the DEBUG mode to make us invencible!

## Put invencibility in DEBUG mode

Just do what this gif is making:<br />
![2026-01-09-21-46-30](https://github.com/user-attachments/assets/9e3cac00-f95e-488e-b651-d2ed0ca948ac)

## Putting the input to activate the DEBUG mode

In code<br />

```
gml_Object_battle_Step_0
```

Before of the lines<br />

```gml
enum UnknownEnum
{
    // anything will be here, idk what is it
}
```

You will put:<br />

```gml
if (keyboard_check_pressed(ord("D")))
    global.debug = !global.debug;
```

## Draw the DEBUG things

In the object<br />

```
battle_enemy
```
You will create the `Draw` code, like this gif:<br />
![2026-01-09-21-30-13](https://github.com/user-attachments/assets/13b1e355-997d-4043-8460-204dcf257c7d)

After this, in this code:<br />

```
gml_Object_battle_enemy_Create_0
```

Before of the **enum UnknownEnums** line, you will put:<br />

```gml
ca = 120;
```

And in the code:<br />

```
gml_Object_battle_enemy_Draw_0
```

(this is the code that we created before, anyways)<br />
We will put this code:<br />

```gml
if (global.debug == 1)
{
    draw_set_font(font_mars_needs_cunnilingus);
    ca++;
    var col = make_color_hsv(ca % 255, 255, 255);
    draw_set_color(col);
    draw_set_alpha(battle_ui.image_alpha);
    draw_text_ext_transformed(480, (392 + battle_ui.y) - 401, "DEBUG", 120, 160, 2, 2, 0);
    draw_set_alpha(1);
    x1 = 480 + (sin(degtorad(ca)) * 20);
    y1 = 392 + (cos(degtorad(ca)) * 20);
    x2 = 480 + (sin(degtorad(ca + 120)) * 20);
    y2 = 392 + (cos(degtorad(ca + 120)) * 20);
    x3 = 480 + (sin(degtorad(ca + 240)) * 20);
    y3 = 392 + (cos(degtorad(ca + 240)) * 20);
    gpu_set_blendmode(bm_add);
    var col1 = make_color_rgb(255, 0, 0);
    var col2 = make_color_rgb(0, 255, 0);
    var col3 = make_color_rgb(0, 0, 255);
    draw_text_ext_transformed_color(x3, (y3 + battle_ui.y) - 401, "DEBUG", 120, 160, 2, 2, 0, col1, col3, col3, col3, battle_ui.image_alpha);
    draw_text_ext_transformed_color(x2, (y2 + battle_ui.y) - 401, "DEBUG", 120, 160, 2, 2, 0, col1, col2, col2, col2, battle_ui.image_alpha);
    draw_text_ext_transformed_color(x1, (y1 + battle_ui.y) - 401, "DEBUG", 120, 160, 2, 2, 0, col1, col1, col1, col1, battle_ui.image_alpha);
    gpu_set_blendmode(bm_normal);
}
```
> **WARNING:** If u not want to copy this code here, this code is avaliable in the Mobile Stuff .zip too!<br />
> (in the location **mobile-controls-location/debug things/**)<br />
> (in this location, there's the **Create** code too!)

# And finished!

It just it! Easy, huh?<br />
I hope you understand how to do it!<br />
Good luck adding it!

