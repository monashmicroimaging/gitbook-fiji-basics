# PART 4: SCALES AND SIZING {#part-5-scales-and-sizing}

For proper presentation of images it is essential to include a scale bar. This allows the viewer to see the scale of the image being presented and make their own conclusions about the data. Calibrating an image is also important if you want to get meaningful size-related measurements out of the image in any later analysis. Calibration is also important when resizing your images. In this section we will show you how to find calibration information from the image, and how to set the scale if the image is not calibrated. We will also demonstrate how to add a scale bar and how to crop and resize images without altering the image data.

This section uses the images **Interstitium 2.tif** and **TrichromeIHC.tif **for demonstration.

## Finding Scale Information in the Image Properties {#finding-scale-information-in-the-image-properties}

In some circumstances FIJI will be able to calibrate your image automatically by reading the attached metadata. This is usually the case for images originally saved in the raw file format.

If the scale is already calibrated the dimensions shown on the image will be in microns instead of pixels.

![](/assets/Part 4/Finding Scale Info/Finding Scale 1 - on image.JPG)

In a calibrated image you can find the scale in microns/pixel by going to **Image -&gt; Properties** \(or use shortcut Ctrl+Shift+P\).

![](/assets/Part 4/Finding Scale Info/Finding Scale 2 - properties menu.JPG)

This will open a display window showing the dimensions of the image and the scale will be automatically populated at the correct size.

For this image we see the scale is automatically set at 2.2microns/pixel.

![](/assets/Part 4/Finding Scale Info/Finding Scale 3 - image properties.JPG)

You do no need to make any changes here, select **OK** or close the window to exit.

You can also find the calibrated scale, this time in pixels/micron, by going to **Analyze -&gt; Set Scale**.

![](/assets/Part 4/Finding Scale Info/Finding Scale 4 -set scale menu.JPG)

Here you will also find the dimensions correctly populated from the metadata if your image was already calibrated.

![](/assets/Part 4/Finding Scale Info/Finding Scale 5 - scale.JPG)

Under **Set Scale** the calibration \(pixels/micron\) is the inverse of that shown under image properties \(microns/pixel\).

You do no need to make any changes here, select **OK** or close the window to exit.

## Finding Scale Information in Metadata {#finding-scale-information-in-metadata}

When opening a file using bio-formats importer you can also find the calibration in the metadata, although this can sometimes be hard to find within the long list of parameters.

To find the calibration in the metadata, ensure **Display** **Metadata** is selected in the bio-formats options as previously described.

![](/assets/Part 4/Finding Scale Info/Finding Scale 6 - Display Metadata.JPG)

The scale information can look different in the metadata of one file compared to another. How it is listed will be dependent on the file type. In this example, if we scroll downt he metadata, we come to the units, listed as microns, and below that, the scale shown as X and Y resolutions of 0.454545. So this gives us the scale of 0.454545 pixels per micron.

![](/assets/Part 4/Finding Scale Info/Finding Scale 7 - Scale in Metadata.JPG)

As shown previously you can also find information from the metadata by going to **Image -&gt; Show Info** \(or shortcut Ctrl + I\). This is useful if you dont need bio-formats importer to open your image.

![](/assets/Part 4/Finding Scale Info/Finding Scale 8 - Image Info Menu.JPG)

You will find the scale information listed here if it was in the image metadata. Again, how it is listed may varry with file type.

![](/assets/Part 4/Finding Scale Info/Finding Scale 9 - Scale in image Info.JPG)

**Note:** Usually if the scale is listed in the metadata, FIJI will scale the images automatically upon opening. If your image is not scaled, you most likely won't find this information in the metadata either.

## Setting the Scale Manually {#setting-the-scale-manually}

For a non-calibrated image, the dimensions of the image will appear in pixels in the top corner of the image.



If you know the conversion factor, you can set the scale manually by inputting the conversion into either the image properties or set scale windows. 

To input the scale via **Image Properties** go to **Image -&gt; Properties** \(or shortcut Ctrl+Shift+P\), as previously described.

![](/assets/Part 4/Finding Scale Info/Finding Scale 2 - properties menu.JPG)

In an uncalibrated image the pixel dimensions will all be displayed as 1. Change the unit of length from pixels to microns and enter the conversion factor in microns \(ie: 1 pixel = x microns\). For the example used here, the calibration in microns/pixel is 0.45.



Select **OK** to save the calibration changes, then save the image to maintain the calibration permanently.

If preferred, you can also input the calibration in pixels/micron via the **Set Scale** tool. To do this, go to **Analyze -&gt; Set Scale**, as previously described.

![](/assets/Part 4/Finding Scale Info/Finding Scale 4 -set scale menu.JPG)

The pixel aspect ratio in the **Set Scale** window will be displayed as 1. To enter the scale, change the unit from pixels to microns and enter either the distance in pixels \(2.222 for this example\) or in microns \(0.45 for this example\)



Select **OK** to save the scale, and save the image.

Whichever method you chose, you will now have a calibrated image that you can easily add a scale bar too, or make accurate measurements on.



## Adding Scale Bars {#adding-scale-bars}

To add a scale bar to your calibrated image, select the image and go to **Analyze -&gt; Tools -&gt; Scale Bar**.

![](/assets/part5/scalebar_menu.jpg)

In the resulting window, enter you scale bar preferences.

![](/assets/part5/scalebar_options.jpg)

Under **width** enter the size you’d like the scale bar to represent.

Enter your **Font** size and select **Colour** and **Location** for the scale bar from the drop down menus.

To show the scale bar only without dimensions check the box next to **Hide text**.

You will see a preview of the scale bar on the image as you make changes. Select **OK** and save the image to save the scale bar.

![](/assets/part5/scalebar_result.jpg)

## Cropping Images {#cropping-images}

You can easily crop an image by drawing an ROI and duplicating the section. Select your ROI tool, as previously described, and draw a region of interest around the area you want to crop.

![](/assets/part5/crop_images_with_duplicate.jpg)

Right click in the selection and choose **Duplicate** from the drop down menu. In the Duplication window you can give the image a new name or keep the default.

![](/assets/part5/duplicate_options.jpg)

Click **OK** to create the duplicate as a new image.

![](/assets/part5/duplicate_result.jpg)

While it is always recommended that you keep the original image uncropped and create a duplicate in this way, you can also crop without creating a duplicate. Select your ROI tool and draw an ROI as above. Then go to **Image -&gt; Crop** \(or use shortcut Ctrl+Shift+X\).

![](/assets/part5/crop_menu.jpg)

This will crop the active image to the selected ROI.

![](/assets/part5/crop_result.jpg)

## Resizing or Scaling Images {#resizing-or-scaling-images}

You can resize, or scale, your image using several different methods. All of these methods resize your image by scaling the pixels. While size changes can be undone until the image is saved, but it is still recommended you work with a duplicate image when making changes to pixel information.

Because these methods alter the pixel information within the image they **should not** be used if any measurements are to be made on the image.

The first method is the **Image Size** tool, which is found under **Image -&gt; Adjust -&gt; Size**.

![](/assets/part5/image_adjust_size_menu.jpg)

This will open the **Resize** options window, where you can enter the new image size in pixels. You can also select to **Constrain Aspect Ratio** for the image and the **Interpolaiton**.

Select **OK** to apply the changes to the image.

![](/assets/part5/image_adjust_size_result.jpg)

Note the difference in the pixel dimensions here following the image resizing.

The next method is the **Scale** tool, which is found under **Image -&gt; Scale** \(or use shortcut Ctrl+E\).

![](/assets/part5/scale_menu.jpg)

![](/assets/part5/scale_options.jpg)

In the **Scale** window, enter the vale by which you want to scale your image \(ie: scale factor of 2 will double the image size, scale factor of 0.5 will halve the image size\). In the Scale tool, the aspect ration will automatically be constrained, when you change the scale factor for X, the Y scale factor will adjust accordingly. The height and width \(in pixel\) will also automatically adjust according to the scale factor entered.

Select **Bilinear** from the **Interpolaiton** drop down menu and select **Average when downsizing**, and **Create new window** so changes will be made to a duplicate image, not the original.

You can give the new image a different name or keep the default. Click **OK** to apply the changes to the image.

A duplicated image at, at the new size, will be created alongside the original image.

![](/assets/part5/scale_result.jpg)

The third method is **Binning**, which is found under **Image -&gt; Transform -&gt; Bin**.

![](/assets/part5/bin_image_menu.jpg)

![](/assets/part5/bin_image_options.jpg)

Binning reduces an image by pixels similar to scaling. In the window enter the **Shrink factor** \(2 x 2 binning will shrink the pixel dimensions by 2, ie: half the image size\).

Select **Average** from the **Bin Method** drop down menu click **OK** to apply the changes to the image.

![](/assets/part5/bin_image_result.jpg)

Note that with binning the image does not appear smaller in dimensions compared to the original but half of the pixels have been removed from the image. Binning is more useful for change the file size than the actual image size dimensions.

The final method is **Scale to DPI**, which is found under **Image -&gt; Adjust -&gt; Scale to DPI**.

![](/assets/part5/scale_dots_per_inch_menu.jpg)

Under **Scale to DPI** you can enter a final image resolution size in dots per inch \(or DPI\) and the image will be scaled accordingly.

Enter your final required DPI in the first box and select the **Interpolation** method from the drop down menu.

Select the check boxes next to **Average when downsizing** and **Create new window**. You can give the resized image a new name if preferred.

Click **OK** to create the new image.

![](/assets/part5/scale_dots_per_inch_options.jpg)

A new window will be created with the re-sized image.

![](/assets/part5/scale_dots_per_inch_result.jpg)

