# Custom Shopify Store Power-ups 🚀
### Power-ups to supercharge your sales

I created several "power-ups" sections to enhance your free Shopify themes. I specifically built these using the free "Dawn" theme, but you can use these power-ups for any theme.

## Here the list of power-ups, in the _order_ they would best appear in a Shopify product page:

### (Screenshots of each of these are coming soon)

* _Image Banner Top_: This goes above the actual product in the product page. You can include brand logos in this.

* _Gallery Tabs_: A quick gallery that goes right under the actual product listing.

* _Flickity UGC Slider_: A video and image slider that shows people creating your product. UGC stands for "User Generated Content", by the way.

* _Benefits slider_: A slider that shows the benefits in text format that you can easily click and drag.

* _Only image_: This goes right above the "hot spots" section. Or if you just want to have a transparent image you can use this for that as well.

* _Hot Spots_: An image of your product that has "blue pulsing spots" on it what lists the benefits on specific parts of your product.

* _Video_: A video with a header (and subtext) included, instead of just the video that Shopify normally has.

* _Reviews header_: Put this right before your reviews widget (Loox, etc). Has 5 stars you can add plus a top quoted review. Make sure it's the same background as the reviews widget you add.

* _Multicolumn benefits_: A multicolumn that guarantees your product is in good shape with the customer. Make sure it's the same color as the footer.

* _As Seen On Logos_: A logo scroller that shows social proof to customers.

* _Custom Counter:_ A social proof counter that can either appear on your About Page or your Homepage (or your main product page). This basically shows your stats.

* _Custom Banner_: Similar to an Image Banner, but it goes on top of any `Page` you like. For example, it works well on top of your `Our Story` page or on the `Contact Us` page. 

>> In fact, your "Our Story" page can have both the `Custom Banner`, the `Custom Counter` right under, then the `Page` section under that (if you're editing a Page in the Shopify Customizer). [Here's a good example][3].

### And for the main HOMEPAGE:

* _Video Banner_: A video that plays at the top of your homepage, preferably when your product is in use. Optionally, you can replace this with the "Image Banner Top" that goes on the tip of your product page.

## Alright, here's the step-by-step on how to use these:

1. In Shopify, get a free theme. Preferably `Dawn`, which was what these power-up sections are built on.

2. Next to your free theme, next to the `Customizer` button, click the 3 dots, and select "Edit code".

3. In the edit code section, under the `assets` folder, click `+ Add a new asset`, click on `Create a blank file` and create 4 files (you'll have to do these one-by-one): `flickity.css`, `powerups.css`, `powerups-mobile.css`, and `flickity.pkgd.min.js` (make sure the "Extension" for this one is `js`). 

> When adding these, make sure you don't add the actual 'text' extension ("css", "js"), as it's already provided to you by Shopify, as long as your "Extension" is correct.

4. Optionally, you can create a 5th file: `newfonts.css` if you want to add custom fonts using `@font-face`.

5. In our repository, go to the [css](../main/css) folder.
> Note: ctrl+click (or command+click on a mac) to open the link in a new tab.

6. Click on the first file: `flickity.css`. Then on the right side, new to "Raw", click on the image that looks like 2 boxes. This copies the raw file.

7. Go back to Shopify and paste it under the `assets/flickity.css` tab. Click Save to save changes.

8. Repeat the previous 2 steps for the following 2 files in the [css](../main/sections) folder: `powerups.css` and `powerups-mobile.css`. (You can optionally do `newfonts.css` if you want to use `@font-face`, which is a custom font either from Google or a 3rd party). Copy each file and paste it in Shopify under the corresponding tab.

9. For `flickity.pkgd.min.js`, that is in our [root](./) folder in our repository. Copy the code there and paste into Shopify under `assets/flickity.pkgd.min.js`.

10. __Now for these to work__, in your Shopify code editor, under the `layout` folder, click on `theme.liquid`.

11. First CLICK anywhere INSIDE the layout/theme.liquid window that appears, then use ctrl + f (or command + f for mac) and search `base.css`. Click "Next".

> You should a line something similar to: `{{ 'base.css' | asset_url | stylesheet_tag }}`

12. Under that base.css line, add these 2 new lines on *separate* lines:
`{{ 'powerups.css' | asset_url | stylesheet_tag }}`
`{{ 'powerups-mobile.css' | asset_url | stylesheet_tag }}`

So it should look like this:
`{{ 'base.css' | asset_url | stylesheet_tag }}`
`{{ 'powerups.css' | asset_url | stylesheet_tag }}`
`{{ 'powerups-mobile.css' | asset_url | stylesheet_tag }}`

> Each code should be on a separate line,
> and it should be __in that order__, or your CSS won't 100% work correctly.

13. Click `Save` to save your changes.

> Optionally, you can add `{{ 'newfonts.css' | asset_url | stylesheet_tag }}` under the "powerups-mobile" code if you want to use a custom `@font-face` font.

14. _Important step:_ To prevent videos from stopping after clicking a product variant in Shopify: In the Shopify code editor, in `assets/media-gallery.js`, CLICK anywhere in the window under that tab. Then use ctrl + f (or command + f on mac) to find this line: `window.pauseAllMedia();`

15. Once you find that line, comment it out. You can simply highlight that line and type `ctrl + /` (or `command + /` on macs) to comment out that line. Click `Save` to save your changes.

16. Finally, add all images in our [assets] folder into Shopify. Simply go to your Shopify dashboard. Then click on "Content", then "Files". Click `Upload files` on the top-right, and add all images for our assets folder into it. These are needed when using some of our power-ups!
 

## Now it's time to add your new power-up sections. Here's how to do it:

[(click here to see a quicker version)][2]

1. Figure out [which power-up from above][1] you want to use. In this example we'll add all of them.

2. In Shopify's code editor, under the `sections` folder, click `+ Add a new section`.

3. Make sure `liquid` is selected. Then look under our [sections](../main/sections) folder to see which power-up you want to add. (All of our power-ups are located here). For example, if you want the __Image Banner Top__, you'll use the `image-banner-top.liquid` file.
    * Simply add the file name `image-banner-top` into the textbox in Shopify. Then click "Done".

4. In our repository, click on the power-up (in this case, `image-banner-top.liquid`). The click on the 2 boxes next to "Raw" to copy the raw code.

5. Back in Shopify's code editor, make sure you're under the right tab that says `sections/image-banner-top.liquid` (or whichever power-up you used). Remove all the code you see, and paste the code you just copied in there. Then click "Save".

6. To use, open a new tab and go back to your Shopify's admin page (or right-click the Exit button's icon on the left side of the page, and select "Open link in new tab". This open another tab in Shopify").

7. In the "Themes" section, click on `Customize`.

8. On the top, where it says `Home page`, click on the dropdown and click on Products > Default Product. __You're now in the Product's page in your Customizer. This is where you'll use all of your powerups__.

9. Under "Template" section, click on `+ Add section` towards the bottom (which is right above the "Footer" section).

10. Click on your new power-up. In this case, it's `Image Banner Top`, which should be towards the bottom.

11. Now you have your power-up. For this one (Image Banner Top), move it to the very top above the "Product Information" to use.

12. Now...it looks weird, right? Good news is there are certain settings needed for this to work. To find those settings, look under the [settings](../main/settings) folder in our repository. In our case, click `image-banner-top-settings.txt` in that settings folder.

13. Follow the settings to know which options to choose. Once the options are right, the design of the power-up will change.

> Note: You MUST use these settings or your power-up will not look right.

14. _Congrats! You just added your first power-up!_ Simply repeat steps 2-13 above to add all of the other power-ups you want. If you want to know what all of the power-ups do, add all of them.

> Important note: For `video.liquid`, do not add that one. Simply [go to the file](../main/sections/video.liquid) and copy the code. Then in your Shopify code editor, under the `assets` folder, click on `video.liquid`.

> Highlight the entire code and paste your code, overwriting what was there before. Then click `Save` to save your changes.


## Here's a quicker version to add all power-ups quickly...

1. Go back to the Shopify code editor tab (which should already be open), and under `sections`, click `+ Add a new section`. Then add the next power-up you want, starting from the top of the list under our [sections](../main/sections) folder (for example: `benefits-slider`). Type that filename and click `Done`.

2. Click `+ Add a new section` once again under the `section` folder, and add the next file under our [sections](../main/sections) folder (`flickity-ugc-slider`). Type that filename in your Shopify code editor and click `Done`. 

3. Repeat step 2 to add the rest of the power-up files in our [sections](../main/sections) folder to your Shopify code editor.
> Note: ctrl+click (or command+click on a mac) to open the link in a new tab.

> Important note: For `video.liquid`, do not add that one. Simply [go to the file](../main/sections/video.liquid) and copy the code. Then in your Shopify code editor, under the `assets` folder, click on `video.liquid`.

> Highlight the entire code and paste your code, overwriting what was there before. Then click `Save` to save your changes.

4. Once all those files are added, go back to each power-up file in our [sections](../main/sections) folder. Click on each file, then copy the code. Paste the code in the Shopify code editor under the CORRECT tab (overwriting what's already there), and click `Save` to save your changes.

5. Once you've added all power-ups code, go to your Customizer tab, and _Refresh the page_. Now you can add your new power-ups under the "Template" section in your Product page!

> [Go back to the top][1] to see the recommended order your power-ups should appear.

6. Important: Make sure you follow the settings for each power-up, located in our [settings](../main/settings) folder! This ensures the power-up looks right and works as intended.



And that's it!

## Final note

I tested these new liquid sections using the free `Dawn` theme in Shopify. I'm not sure if they are compatible with any other free Shopify theme. 

You can always test it out to find out. Other than that, enjoy your new powerups!

~ Victor

[1]: ../main?tab=readme-ov-file#here-the-list-of-power-ups-in-the-order-they-would-best-appear-in-a-shopify-product-page

[2]: ../main#heres-a-quicker-version-to-add-all-power-ups-quickly

[3]: https://www.ventyfan.com/pages/about-us