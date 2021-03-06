# ColorSlider
Simple color picker library for Android

[![](https://jitpack.io/v/naz013/ColorSlider.svg)](https://jitpack.io/#naz013/ColorSlider)

Screenshot

<img src="https://github.com/naz013/ColorSlider/raw/master/res/screenshot.png" width="400" alt="Screenshot">

Sample APP
--------
[Download](https://github.com/naz013/ColorSlider/raw/master/app/release/app-release.apk)

[Google Play](https://play.google.com/store/apps/details?id=com.colorslider.example)

Download
--------
Download latest version with Gradle:
```groovy
repositories {
    maven { url 'https://jitpack.io' }
}

dependencies {
    implementation 'com.github.naz013:ColorSlider:1.0.6'
}
```

AndroidX version:
```groovy
dependencies {
    implementation 'com.github.naz013:ColorSlider:2.0.6'
}
```

Usage
-----
Default (Material colors picker):
```xml
<com.github.naz013.colorslider.ColorSlider
        android:id="@+id/color_slider"
        android:layout_width="match_parent"
        android:layout_height="36dp" />
```
Gradient (Params: cs_from_color, cs_to_color, cs_steps):
via XML:
```xml
<com.github.naz013.colorslider.ColorSlider
        android:id="@+id/color_slider"
        android:layout_width="match_parent"
        app:cs_from_color="#F44336"
        app:cs_steps="500"
        app:cs_to_color="#40F44336"
        android:layout_height="36dp" />
```
in code:
```java
colorSlider.setGradient(@ColorInt int fromColor, @ColorInt int toColor, int steps)
```

Gradient from array of colors:
in code:
```java
colorSlider.setGradient(@ColorInt int[] colors, int steps)
```


Array of color resources (Params: cs_colors):
via XML:
```xml
<com.github.naz013.colorslider.ColorSlider
        android:id="@+id/color_slider"
        android:layout_width="match_parent"
        app:cs_colors="@array/colors"
        android:layout_height="36dp" />
```
in code:
```java
colorSlider.setColors(@ColorInt int[] colors)
```


String array of hex colors (Params: cs_hex_colors):
via XML:
```xml
<com.github.naz013.colorslider.ColorSlider
        android:id="@+id/color_slider"
        android:layout_width="match_parent"
        app:cs_hex_colors="@array/hex_colors"
        android:layout_height="36dp" />
```
in code:
```java
colorSlider.setHexColors(String[] hexColors)
```

Also you can set listener for color picker:
```java
colorSlider.setListener(new ColorSlider.OnColorSelectedListener() {
        @Override
        public void onColorChanged(int position, int color) {
            updateView(color);
        }
    })
```


License
-------

    Copyright 2019 Nazar Suhovich

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
