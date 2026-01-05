---
layout: post
title:  "List of annoying Android bugs you should know about"
date:   2017-02-10
categories: Android
---

There is a bug in Android where if you create a Custom drawable and don't overload the getConstantState() method, your app will crash when you call `layerDrawable.mutate();`

This caused our app to crash with the new `BottomNavigationView` because in the code for the drawable, it calls drawable.mutate(); to tint the selected buttons.

Hence why it's important to override `Drawable.getConstantState()`
`drawableStart` and `drawableEnd` tint

Yes there is a bug from Android 5.0 until 6.0 that was fixed in 7.0 where `drawableTint` doesn't apply on `drawableStart` and `drawableEnd`

Some solutions can be used

* Use drawableLeft `drawableRight` (You will get warnings about left to right support)
* Set the drawable tint in code
* Create multiple drawable resource for each colors
