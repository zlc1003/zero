<head>
<style type="text/css">
    .a {
        margin-inline: 2px 4px;
        width: 40px;
        height: 40px;
        vertical-align: text-bottom;
    }
</style>
</head>

# 如何在网页中加入<img xmlns:html="http://www.w3.org/1999/xhtml" src="https://zlc1003.github.io/apple.svg" data-l10n-name="a" class="a">

## 在网页的head部分加入

```html
<style type="text/css">
    .a {
        margin-inline: 2px 4px;
        width: 20px;
        height: 20px;
        vertical-align: text-bottom;
    }
</style>
```

## 然后在body部分需要的地方加入

```html
<img xmlns:html="http://www.w3.org/1999/xhtml" src="https://zlc1003.github.io/apple.svg" data-l10n-name="a" class="a">
```