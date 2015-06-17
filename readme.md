#Image Preloader
A utility for loading anc caching background images before they're required. This is useful if you have a background image that should only be displayed when an element is in a certain state, e.g. `:hover`. If you preload the image, the user won't need to wait for it to download once the state is applied.

##Usage
1. Import the partial into your project before any images that require preloading.
2. Use the `preload-image` function for any background images you want preloaded:

```
input:invalid {
    background-image: preload-image('/images/cross.gif');
}
```

3. Load the images by applying the `load-images` mixin to an otherwise arbitrary element. We suggest using a psuedo-element:

```
body:after {
    @include load-images();
}
```

The browser will request your images on page load and they should be ready when required.