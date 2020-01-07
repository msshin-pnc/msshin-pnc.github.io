---
layout: post
title:  "[Android Studio] Android 언어 변경"
date:   2020-01-07 09:39:00 +0900
categories: android
comments: true
background: '/img/posts/06.jpg'
---

# 1. **LocalePicker** 사용

## 1-1. 지원하는 언어 목록 가져오기

```java
private List<LocalePicker.LocaleInfo> getLocaleInfoList(){
    List<LocalePicker.LocaleInfo> localeInfoList = LocalePicker.getAllAssetLocales(this, false);
    for (LocalePicker.LocaleInfo localeInfo : mLocaleInfoList) {
        if(DEBUG) Log.d(TAG, localeInfo.getLocale() + ", " + localeInfo.getLabel());
    }
    return localeInfoList;
}
```

## 1-2. 가져온 언어 목록 중 선택하여 언어 변경하기

```java
private void setLocaleInfo(LocalePicker.LocaleInfo localeInfo){
    LocalePicker.updateLocale(localeInfo.getLocale());
}
```