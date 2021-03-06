[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.github.greasemonk/spannablebar/badge.svg?style=flat)](https://maven-badges.herokuapp.com/maven-central/com.github.greasemonk/spannablebar)
[![API](https://img.shields.io/badge/API-16%2B-yellow.svg?style=flat)](https://android-arsenal.com/api?level=16)  
[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-SpannableBar-brightgreen.svg?style=flat)]()

SpannableBar 
===================

SpannableBar is a Grid-style spannable bar, that is useful when you need a way to span a bar over columns. The view allows you to set the starting column, the span, the number of columns, and more.

I have personally spent days to GridView, GridLayout and TableLayout but have been unable to SIMPLY make a 'bar' that spans over a couple of columns, with the possibility to set the start as well.
Even if that would work, those views would be too over complicated with a lot of features I did not need.

I decided to create a custom view that does only what I needed it to be.

The following example usage is from the [TimeTable](https://github.com/GreaseMonk/android-timetable-core) repository
Here you can see a timetable where SpannableBars are used in each row item.

![example application](https://github.com/GreaseMonk/android-timetable-core/blob/master/images/device-2016-11-23-162112.png) 

# Installation

Include the following in your build.gradle as a dependency:

```gradle
dependencies {
  compile 'com.github.greasemonk:spannablebar:1.0.1'
}
```

If this fails, make sure to check if you have synchronized your local repositories.

In IntelliJ or Android Studio, you can find this under Settings>Build,Execution,Deployment>Build Tools>Maven>Repositories.


# Usage

Include the layout in your XML:

```xml
<com.greasemonk.spannablebar.SpannableBar
            android:layout_width="match_parent"
            android:layout_height="48dp"
            android:id="@+id/bar"/>
```

Some optional XML properties include:
```xml
xmlns:app="http://schemas.android.com/apk/res-auto"

app:barText="my text"
app:barTextColor="@android:color/white"         // Default is DEFAULT_TEXT_COLOR -> Color.WHITE
app:barColor="@android:color/holo_blue_light"   // Default is DEFAULT_BAR_COLOR -> Color.LTGRAY
```

Set the bar's properties:

```java
SpannableBar bar = (SpannableBar) findViewById(R.id.bar);

// Sets all the properties in one go
bar.setProperties(int start, int span, int columnCount);

bar.setColumnCount(int numColumns);   // Default is SpannableBar.DEFAULT_COLUMN_COUNT -> 7
bar.setStart(int start);              // Default is SpannableBar.DEFAULT_START -> 0
bar.setSpan(int span);                // Default is SpannableBar.DEFAULT_SPAN -> 7

// Optionally set the corner radius (for all corners)
bar.setRadius(float radius)           // Default is 0  (this will be fixed later, should be SpannableBar.DEFAULT_RADIUS -> 8f  for 48dp
bar.setColor(int color)
bar.setTextAlignment(Paint.Align align)
bar.setShowCellLines(boolean show)
bar.setCellLineColor(int color)
bar.setTextTypeface(Typeface typeface)
```


