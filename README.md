# DrawingCanvas

[![GitHub license](https://img.shields.io/badge/License-GPL3.0-blue.svg)](LICENSE)

Library for drawing app canvas with features like undo redo, color & transperency change, Integrated into your app easily.

#### Look at it's *working demo* on <a href="https://play.google.com/store/apps/details?id=com.mihir.drawingapp"> **Playstore**</a>.


## Features
- **Size** , **transperancy** and **color** manipulation of brush
 -- Using ***setSizeForBrush(), setBrushAlpha() and setBrushColor()*** respectively
- **Undo** and **Redo** fucntionality available
-- Using ***undo() and redo()*** respectively
- Using **erase()** function to match the background color to the brush color
- **Clear canvas** feature
-- Using ***clearDrawingBoard()***
- Getter methods to get the current values of the attribute and also the drawing itself.

## Demo

Watch the explaination on youtube: https://www.youtube.com/watch?v=Dnm3SI_OIko

https://user-images.githubusercontent.com/66465511/126068320-9d1f0971-2f0f-4ba7-a16e-9815aacb32ee.mp4

## How to use

### You can refer to this Video:
https://youtu.be/Dnm3SI_OIko

### OR Follow these steps:
> Step 1. Add this maven *dependency* to your build.gradle (project) file / settings.gradle for new version

```gradle
allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
  ```
 >Step 2. Add the *dependency* to your build.gradle (app) file
 
 ```gradle
 dependencies {
	        implementation 'com.github.Miihir79:DrawingCanvas:1.1.2'
	}
  ```
  
  >Step 3. *Add* the XML code 
  
  ```XML
  <com.mihir.drawingcanvas.drawingView
        android:id="@+id/drawing_view"
        android:layout_width="match_parent"
        android:layout_height="match_parent">

    </com.mihir.drawingcanvas.drawingView>
```

>Step 4. *Refrence* the canvas in XML to use it's functions

```Kotlin
    drawing_view.setBrushAlpha(120)// values from 0-255
    drawing_view.setBrushColor(R.color.white) 
    drawing_view.setSizeForBrush(12) // takes value from 0-200
    drawing_view.undo() 
    drawing_view.redo()
    drawing_view.erase(Color.WHITE) // give the color same as the background color
    drawing_view.clearDrawingBoard()
    
    //getter methods
    val alpha = drawing_view.getBrushAlpha() // returns INT
    val brushSize = drawing_view.getBrushSize() // returns INT
    val brushColor = drawing_view.getBrushColor() // returns INT
    
    val drawing = drawing_view.getDrawing() // returns ArrayList<CustomPath>(); where CustomPath(var color:Int , var brushThickness:Int, var alpha:Int)
        
```

### Functions

| Explanation               | Parameter Name          | Type       |  Values        |
| ------------------------- | ----------------------- | ---------- | -------------- |
| Set Brush Color           | **setBrushColor()**     | color      | *any color*    | 
| Set Brush Alpha           | **setBrushAlpha()**     | Int  	   | *0-255*        |
| Set Brush Size            | **setSizeForBrush()**   | Int        | *0-200*        |
| Set eraser color          | **erase()**             | color      | *any color*    | 

## Demo of all the functions
### setBrushAlpha

This function takes the value from *0-255*. You can check it's implementation here:<br>

<img src="https://user-images.githubusercontent.com/66465511/126197548-15777ce6-c18e-41b4-b119-4dfda6c5eb23.gif" width="250" />

### setBrushColor

This function takes *any color* as an input. You can check it's implementation here: 

<img src="https://user-images.githubusercontent.com/66465511/126198881-8496b4eb-4646-435f-b480-2bc623db1089.gif" width="250" />

Link for the color picker: https://github.com/Dhaval2404/ColorPicker

### setSizeForBrush

This function takes any value from *0-200* as an input. You can check it's implementation here: 

<img src="https://user-images.githubusercontent.com/66465511/126199495-a1e4cc19-5a06-48f6-b6a8-f1301c82db1f.gif" width="250" />

### undo and redo

These functions can *undo and redo* your strokes. You can check it's implementation here: 

<img src="https://user-images.githubusercontent.com/66465511/126199690-74ff6303-e18c-4b7b-9d07-c20bb27c492a.gif" width="250" />

### clearDrawingBoard

This function *clears all the strokes and clear the drawing board*. But carefully **you wont be able to undo this change!** You can check it's implementation here: 

<img src="https://user-images.githubusercontent.com/66465511/126199980-e8a1137b-4f47-4989-8db9-f2e76c0b6f8f.gif" width="250" />

### getBrushAlpha
This functions **returns** *Integer value* of alpha of the brush which will be in the range of 0-255.

### getBrushSize
This function **returns** *Integer value* of the size or thickness of the brush.

### getBrushColor
This function **returns** *Integer value* of the color of the brush.

### getDrawing
This function **returns** an entire *arraylist of customPath* where CustomPath(var color:Int , var brushThickness:Int, var alpha:Int). Here color is the brush color , brushThickness is the width or the size of the brush and alpha is the transperancy. This is useful to store the entire drawing in high resolution or to share it.

## That's it!
If you liked it then show some love by giving a star.
<br>
## Author and contributions:
Mihir Shah has made this library and will maintain it.
<br>
#### All contributions are welcomed!
