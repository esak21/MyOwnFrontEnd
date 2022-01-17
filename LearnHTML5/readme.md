# HTML 
----------
ol and ul are indented by default  <br>
```
images are self closing , so there wont be any closing tag 
```
images are not valid without the alt attributes , basically it is used to describe the image </br>

## Layout HTML TAGS 
- Header 
- footer 
- main 
- div (generic) 
    - used to create boxes  
- nav 
- section 
# css #
css is all about key value Pair 
<br>
`property: value ;`

## property is what we want to change like color font-size font-weight 
## values are what we want to set that property to like 20px 

</br>

# Different ways to add css to the Page 
- Inline Stying 
    - within the tag we are going to add a attribute called `style `. In which we can write our css code 

- External Styling 
    - 

- Internal CSS 
    - we need to use the `style tag` in the Head Tag 
    - ``` h1 { color: #4e4e4e ;}```
    - 

-  External CSS 
    - One File to control all the pages


- Selector 
    - Element Selector 
    - class selector 
        - we use `.`
        - class for groups 
        - we can use class for over and over again 
        - Spaces causes Problems , if we want to have 2 different name use - / _ to join both words 
        - ```   
            ```
        - 
    - id selector 
        - we use the `#` selector
        - id is for individual 
        - ID can be used only once within the page 
        - ID Will override the class if they are both selecting the same thing 




# Block Model 
    - Most elements are block level element by default 
    - They have the width of 100% of their parent
    - They have height of 0 , but the height might grow to match the content 
    - They stack one on top of other 
    - ** We can control the width and height of the Element **
    - 

## Margin And Padding 
- Essentials to the Box Model 
- Margins are used to control the position of element relative to those around it. `Outside of the element`
- margin-left, marging-righr, margin-top,margin-bottom

    we can also write margin in short hand  <br>
    ` margin use the clock wise Style`
    '` Top Right bottom left `'
    margin: 10px 20px 30px 40px 


## Padding 
- padding is used to control the positioning  of content inside our element 
- it works just like margin in terms of the long form and shorthand properties 
- if i add padding it will moved from the side of the box model , 

# Margin add empty space to outside 
# padding add empty space to Inside 

# Borders
- Borders add a border around your element 
- it take 3 properties to set a border width style color 
- if we dont specify the color it will pick up the text color 

```
border-width: 3px 
border-style : solid
border-color : yello 
```


Overall box model <br>

![alt text](/LearnHTML5/picture/border.png)


    if we use marging: auto it will add empty space on both left and right side which makes the element to be at exactly in the center position
    ** it must have width Property 

So far if we look at the Page we have some space at all the Four Corners of the page , reason is that by default all the browsers are having this space , to overcome that we need to update the body margin to 0 


# Lets Create Column 
## flexbox 

```
By Default when setting display:flex on a elmenet all the children will become columns

.columns {
    width: 750px; 
    display: flex;
    margin: auto
}

```

<br>
<br>
<br>

# CSS GRID 

- Grids are very useful to create 2-dimensional layout
- 

if we want to create a 2 Column and 3 rows then 
```

.container {
    display: grid;
    grid-template-columns: 100px auto;
    grid-template-rows: 50px 50px 100px;
    grid-gap: 3px;

}

```

if we want our grid to grow and shrink automatically for all the Columns we have to use fr unit 
`1 fr unit` - it means Grid will convert the entire space/width into 3 equal fraction and each column will get one fraction Unit 

same unit can be re write into 
repeat(3,1fr)

### Short hand Methods
<br>

    Here grid-template(row,column)

    .container {
    display: grid;
    grid-template: repeat(3,1fr)/ repeat(3,1fr);
    grid-gap: 3px;

    }

## How to Update the Size in the GRID 

## How to Update the Header to Take entire Column 

if we have 2 Column then we have 3 Column Line 

    .header {
    grid-column-start: 1;
    grid-column-end: 3;
    }

    we can also write it as 
    .footer {
    grid-column: 1/span 2 ;
    }

    -1 upto the last column line
    .footer {
    grid-column: 1/-1;
    }

For the Grid and it Shows in the Right Hand Side 
```
.container {
  display: grid;
  grid-gap: 5px;
  grid-template-rows: 50px 200px 50px;
  grid-template-columns: repeat(12, 1fr);
  border: blueviolet 5px solid;
}

.header {
  grid-column: 1 / -1; 
}
.menu {
  grid-row: 1 / -1 ;
  grid-column: -1 / -1
}
.content {
  grid-column: 1/ -1;
}

.footer {
  grid-column: 1 / -1;
}
```


## For Creating Protype Layout quickly - template area 

Another Way of defining the Template
```
.container {
  height:100%;
  display: grid;
  grid-gap: 5px;
  grid-template-rows: 50px auto 50px;
  grid-template-columns: repeat(12, 1fr);
  grid-template-areas: 
  "h h h h h h h h h h h h "
  "m c c c c c c c c c c c"
  "f f f f f f f f f f f f";
}

.header {
  /* grid-column: 1 / -1;  */
  /* Grid Area  */
  grid-area: h;
}
.menu {
  grid-area: m;
}
.content {
  /* grid-column: 2/ -1; */
  grid-area: c;
}

.footer {
  /* grid-column: 1 / -1; */
  grid-area: f;
}
```


# Adding Responsiveness to the PAge 

```
.container {
    display: grid;
    grid-gap: 5px;
    grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
    grid-template-rows: repeat(2, 100px);
}
```

### implicit Rows 
```
.container {
    display: grid;
    grid-gap: 5px;
    grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
    grid-auto-rows: 75px;
    grid-auto-flow: dense;
}

.horizontal {
    grid-column: span 2;
}

.vertical {
    grid-row: span 2;
}

.big {
    grid-column: span 2;
    grid-row: span 2;
}

```

