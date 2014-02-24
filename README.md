CropView
========

How to use:

Create in you XML layout TouchCropView:

```android
<YOUR_PACKAGE_NAME.TouchCropView
        android:id="@+id/images"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentBottom="true"
        android:layout_alignParentLeft="true"
        android:adjustViewBounds="true" />'
```       
        
In you on create find the view and set getViewTreeObserver().addOnGlobalLayoutListener the get the view size when an image is attached to him.

```java
drawing = (TouchCropView) findViewById(R.id.images);
drawing.getViewTreeObserver().addOnGlobalLayoutListener(
new ViewTreeObserver.OnGlobalLayoutListener() {
public void onGlobalLayout() {

if(cameraBitMap != null)
{

float scaledHeight = (float) cameraBitMap.getHeight()/ (float) drawing.getHeight();
float scaledWidth = (float) cameraBitMap.getWidth()/ (float) drawing.getWidth();

drawing.setScaledSize(scaledHeight, scaledWidth);

}
}
});
```

When you want to add an image to the view call also this method:

```java
drawing.setImageBitmap(cameraBitMap);
```

When you want to take the user input call:

```java
drawing.getCropedBitmap();
```

When you want to clear the user input:

```java
drawing.clear();
drawing.setBitmap(cameraBitMap);
```

Look at the example code and watch it work

        
        
