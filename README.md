# DiagonalLinesView

`DiagonalLinesView` is a custom Android view that draws diagonal lines across its canvas. It can be used to create visually appealing backgrounds or patterns in your Android applications.

## Features
- Draws evenly spaced diagonal lines in two directions (top-left to bottom-right and top-right to bottom-left).
- Fully customizable via code for line color and thickness.
- Easily integrated into any Android project.
- Can be used as a background for other views or as part of a `CardView` layout.

---

## Installation

1. Add the `DiagonalLinesView` class to your project:
   - Copy the `DiagonalLinesView` code into your project under the desired package directory.

2. Use the view in your layout XML or programmatically.

Replace the package name `ir.applicore.kingmovie` in the class file with your own package path.

---

## Usage

### Use as View Background
You can use `DiagonalLinesView` as a background in two ways:

#### 1. XML Layout
To use `DiagonalLinesView` in your XML layout:

```xml
<your.package.path.DiagonalLinesView
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#FFFFFF" />
```

#### 2. Jetpack Compose
If you are using Jetpack Compose, you can wrap `DiagonalLinesView` in an `AndroidView` composable:

```kotlin
import androidx.compose.ui.viewinterop.AndroidView
import your.package.path.DiagonalLinesView

@Composable
fun DiagonalLinesBackground() {
    AndroidView(factory = { context ->
        DiagonalLinesView(context).apply {
            // Optional customization
        }
    }, modifier = Modifier.fillMaxSize())
}
```

### Use in a CardView Layout
You can use `DiagonalLinesView` as a background inside a `CardView` and place a button or other components on top of it. Example:

#### XML Example
```xml
<androidx.cardview.widget.CardView
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    app:cardCornerRadius="16dp"
    app:cardElevation="8dp">

    <FrameLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent">

        <your.package.path.DiagonalLinesView
            android:layout_width="match_parent"
            android:layout_height="match_parent" />

        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="center"
            android:text="Click Me" />

    </FrameLayout>
</androidx.cardview.widget.CardView>
```

#### Jetpack Compose Example
```kotlin
import androidx.compose.foundation.layout.*
import androidx.compose.material.Card
import androidx.compose.material.Button
import androidx.compose.material.Text
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.unit.dp
import androidx.compose.ui.viewinterop.AndroidView
import your.package.path.DiagonalLinesView

@Composable
fun CardWithDiagonalLines() {
    Card(
        elevation = 8.dp,
        modifier = Modifier.padding(16.dp)
    ) {
        Box(modifier = Modifier.size(200.dp)) {
            AndroidView(factory = { context ->
                DiagonalLinesView(context)
            }, modifier = Modifier.fillMaxSize())

            Button(onClick = { /* Do something */ },
                modifier = Modifier.align(Alignment.Center)) {
                Text("Click Me")
            }
        }
    }
}
```

---

## Customization

### Change Line Color
To change the line color, modify the following line in the `init()` method:

```java
linePaint.setColor(Color.parseColor("#217CF3")); // Replace with your desired color
```

### Change Line Thickness
To adjust the line thickness, modify the following line in the `init()` method:

```java
linePaint.setStrokeWidth(2); // Replace with your desired thickness
```

---

## Example
Below is an example of a screen using the `DiagonalLinesView` as a background:

![Diagonal Lines Example](https://via.placeholder.com/800x400.png?text=Diagonal+Lines+Example)

---

## Author

Developed by [ThingCoder](https://github.com/your-profile).

