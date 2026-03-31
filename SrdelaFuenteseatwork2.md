# Seatwork #2 - Getting to know CSS Position and z-index.
### This seatwork will ask you to implement the different CSS position on a given code.
### short link to this .md file is: https://bit.ly/4c61P9K
#### Resources (also found in Khub week 5)
- [4 Minute Youtube Video on CSS Position](https://www.youtube.com/watch?v=YEmdHbQBCSQ)
- [CSS Position Tutorial](https://roycan.github.io/CssPositioningZIndexLab/)

### Instructions: 
1. This is individual submission in khub, but you can work with a partner.  When you submit in khub please place both your names in the submission bin.
2. Guided Activity (30 minutes), please follow what is being required.  

    - Make a copy of this .md file to your Q4 repository and name it as **SectionLNseatwork2.md** example **9LiCruzSeatwork2.md**. Place it in your q4 repository vscode local computer. Committing frequently to your Github repository.  
    - Copy the code below and paste it inside a new file (name it as SectionLNseatwork2.html). Place this file in the same location where the .md file is saved. 
    - Change the content values of the meta tags to your names for author/s and the date today for revised.
    - Please do the following tasks that will ask you to reposition HTML elements then answer the guided question for each task on the .md file. Commit changes to the .md file and to the .html file as well.
    **- This seatwork is worth 20pts and should be submitted by the end of the period** The link to [KHub submission bin](https://khub.mc.pshs.edu.ph/mod/assign/view.php?id=15481).
      - Submit the links to your .md file and .html file.

```html
<!DOCTYPE html>
<html>
<head>
  <meta name="author" content="<your names>" />
  <meta name="revised" content="<date today>" />
  <style>
    body { font-family: Arial, sans-serif; }
    .header, .footer {
      background: lightblue;
      padding: 10px;
    }
    .footer {
       opacity: 0.5;
    }
    .sidebar {
      background: lightgreen;
      width: 150px;
      height: 200px;
    }
    .content {
      background: lightyellow;
      width: 300px;
      height: 200px;
    }    
  </style>
</head>
<body>
  <div class="header">Header</div>
  <div class="sidebar">Sidebar</div>
  <div class="content">Main Content</div>
  <div class="footer">Footer</div>
</body>
</html>
```
### Step 1 (Static vs Relative):

- Add in css ```position: relative; top: 20px; left: 20px;``` to .sidebar.

- Guided Question: What changed compared to the default static positioning? Try to give different values to top and left or you can change it to bottom, right.

A major thing that changed upon adding the "position" element is that the sidebar did in fact move its position, regardless of whether or not there is already text or element within the area the sidebar will cover.

### Step 2 (Fixed):

- Add in css ```position: fixed; bottom: 0; width: 100%;``` to .footer.

- Guided Question: What happens when you scroll the page? Why does the footer behave differently from position relative?

Upon scrolling the page, the footer is seen to be "fixed" at the bottom of the page. The footer behaves differently in this manner due to its position now being "fixed" instead of it being "relative" to its original position.

### Step 3 (Absolute):

- Add in css ```position: absolute; top: 66px; left: 200px;``` to .content.

- Guided Question: What is the effect of position: absolute on an element? How is it different from fixed?

The effect of "position: absolute" on an element is that the element now "floats" over other content without pushing said content around. Unlike "position: fixed", an absolute position means an element scrolls with the page, whereas a fixed position means the element stays pinned on the screen.

### Step 4 : (Absolute)

- Add in html ```<div class="notice">Notice!</div>``` and include the css below:

```css
.notice {
    position: absolute;
    top: 60px;
    left: 400px;
    background: orange;
    padding: 10px;
    z-index: 2;
}
```

- Give .content a z-index: 1.

- Guided Question: Why does the notice appear on top of the content? What happens if you swap the z‑index values?

The notice appears on top of the context due to its z-index being of the value 2. If you swap the z-index values, the notice will no longer be on top of the content. Think of z-index values as layers, wherein the greater the number, the higher the layer.

- Challenge: 
    * What changes that you have to do on the code that will position .notice box on the top right corner of the .content box? Please write the code on paper as well (both html and css on the part of .notice and .content).
    
    <div class="content">
    <div class="notice">Notice!</div>
  </div>

  .content {
      background: lightyellow;
      width: 300px;
      height: 200px;
      position: relative;
      z-index: 1;
    }
    .notice {
      position: absolute; // for it to be relative to its nearest parent
      top: 0; 
      right: 0; 
      background: orange;
      padding: 10px;
      z-index: 2;
    }
    * Try to change the position of .content to relative then to fixed. What do you observed each time?

    Upon changing the position to relative and fixed alternatively, I observed that the content box (light yellow in color) would go directly below the side bar when the position is set to relative. Meanwhile, for position: fixed, I observed the content box moved beside the sidebar.

    * What do you observe on about the effect of z-index on .notice and .content boxes?

    The z-index values act as "layers" for elements. The greater the number, the higher the layer.

3. Please answer the following reflection questions (15 minutes)

    a. Could you summarize the differences between the CSS position values (static, relative, absolute, fixed)? 

    Static: default; elements follow order of HTML code
    Relative: element positions itself relative to another
    Absolute: element positions itself based on the closest parent element
    Fixed: element sticks on the browser screen; does not move

    b. How does absolute positioning depend on its parent element?

    An absolute positioning looks for the closest parent element to it and uses the parent's edges as its reference points. In case there is no parent element, the element uses the webpage (body) as its reference points or boundaries.

    c. How do you differentiate sticky from fixed (you can research on sticky)?

    Fixed will stay in place no matter how much you scroll. Sticky will stay on the screen as you scroll until it hits a certain point, then it will stop being "stuck" on the screen. The element will only stay "stuck" on the screen while it is still within its parent container, otherwise, it will not be stuck on the screen after scrolling past the container.

    d. If you were designing a webpage for a school event, how might you use positioning to highlight important information? Please give concrete examples.

    If I were to design a webpage for a school event, particularly a school fair, I would use the "sticky" position for a button that leads to the fair schedule.
