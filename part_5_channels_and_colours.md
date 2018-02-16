# PART 6: CHANNELS AND COLOURS {#part-6-channels-and-colours}

Immunofluorescence experiments are almost always captured on highly sensitive monochrome cameras. This means that each fluorophore is captured as a different image with no associated colour. Often you will want to add colour to each channel \(usually in the colour of the fluorophores emission\) and to create composite images of 2 or more of the channels combined. This section will show you how to arrange and alter multi-channel images and change the colour of your images.

We will use the images _NeuralTube.jpg_ plus _NeuralTube Blue Saturated.tif_ and _TrichromeIHC.tif_ throughout this section, along with the image set _‘RGB- blue.tif, RGB-green.tif and RGB-red.tif'_.

## Bit Depth {#bit-depth}

The bit depth of an image essentially determines the number of colours that can be displayed within that image. The number of colours \(also referred to as dynamic range\) can be calculated by the simple equation: 2^bit-depth.

| Bit Depth | Dynamic Range |
| :---: | :---: |
| 8-bit | 0 - 255 \(or 256 colours\) |
| 12-bit | 0 - 4,095 \(or 4,096 colours\) |
| 14-bit | 0 - 16,383 \(or 16,384 colours\) |
| 16-bit | 0 - 65,535 \(or 65,536 colours\) |
| 24-bit \(also called 24-bit RGB = 3 x 8-bit channels\) | 0 - 16,777,215 \(or 16,777,216 colours\) |

The bit depth of an image will be determined by the camera that the image was captured on. Most images are captured on 8-bit, 12-bit, 14-bit or 16-bit cameras. Three colour fluorescent images are RGB 24-bit format \(made up of 3 x 8-bit colour channels\).

It is helpful to know the bit depth of the camera used to capture your images so you know the dynamic range of your colours.

8-bit or RGB are the format most standard image viewers and presentation software will show. Images at other bit-depths may appear as black boxes. To allow any software to display your image correctly you can change the bit depth to 8-bit or 24-bit RGB very simply.

Select your image then navigate to **Image -&gt; Type** and select **8-bit** or **RGB Color** from the list.

![](/assets/Part 5/Bit Depth/Bit Depth 1 - Menu.jpg)

Likewise, some functions of FIJI will not work on an RGB 24-bit image \(ie: thresholding\). You can convert a single channel RGB image to 8-bit using the same steps as above, but selecting **8-bit** from the choices. In a merged RGB image you can also create 3 x 8-bit images by splitting channels as shown below.

**Note:** _DO NOT_ alter bit and colour depth if you plan to do any analysis on the image, always work on a duplicate image and/or save the results of the conversion as a separate file to preserve your original image.

## Split Channels {#split-channels}

To separate the channels in a merged image go to **Image -&gt; Color -&gt; Split Channels**.

![](/assets/Part 5/Split Channels/Split 1 - Menu.jpg)

This will automatically detect and separate red, green and blue into individual monochrome images.

![](/assets/Part 5/Split Channels/Split 2 - Original to split.jpg)

The channel will be identified for each image next to the image name.

![](/assets/Part 5/Split Channels/Split 4 - channel label.jpg)

## Assigning or Changing Image Colours Using LUTs {#assigning-or-changing-image-colours-using-luts}

Monochrome images have a grey look up table applied, meaning that each intensity is represented by a different shade of grey. In single channel images this can easily be changed to be different shades of red, green, blue etc. by simply changing the applied look up table \(LUT\).

Click on the image you want to change and then go to **Image -&gt; LUTS** and select the colour/LUT you want to apply to the image.

A red LUT has now been applied to this image.

You can also find LUTs from the **LUT** icon in the tool bar. Click the icon to open the list of LUTs and select the one you want to apply to your image.

## Merge Channels {#merge-channels}

If you have individual images of channels that you want to merge, select **Image -&gt; Color -&gt; Merge Channels**.

![](/assets/part6/merge_channels_menu.jpg)

A window will open with different channel/colour options. It will attempt to automatically input the correct images into the different channel options. If they are loaded incorrectly you can assign the individual images to the correct channel using the drop down menus.

![](/assets/part6/merge_channels_options.jpg)

If you want to keep the original single channel images open, check the box next to **Keep source images.** For a simple merge, where you do not want to continue altering individual channels you can uncheck **Create composite.** However, if you want to make further alterations to channels within the merged image, keep this box selected.

Select **OK** to create the merged image.

![](/assets/part6/merge_channels_examples.png)

## Channels Tool {#channels-tool}

A composite image will present as a stack with each channel represented by one slice of that stack. To make alterations to channels within a composite image you can use the channels tools. To open this tool, go to **Image -&gt; Color -&gt; Channels Tool** \(or use shortcut Ctrl+Shift+Z\).

![](/assets/part6/channel_tool_menu.jpg)

In the **Channels** tool window you can select from the dropdown menu whether you want to work in composite mode, colour or greyscale.

![](/assets/part6/channel_tool_options.jpg)

In **Composite** mode – all images in the stack will appear to be a merged RGB image, however the active channel will be shown by the colour box surrounding the image.

In **Color** – each channel be displayed as an individual image in the stack in the assigned colour.

In **Grayscale** – each channel will be displayed as an individual image in the stack in grey.

In colour and greyscale you can switch between channels by selecting the check boxes next to the channel or by moving the slider at the bottom of the image.

![](/assets/part6/channel_tool_example1.jpg)

When working in composite mode you can turn channels on and off by checking, or unchecking, the box beside that channel. In the example below we turn off the DAPI, or blue channel, by unchecking the box beside channel 3. Channels are ordered Red-Green-Blue \(RGB\).

![](/assets/part6/channel_tool_example2.jpg)

You can convert the composite to RGB at any time by selecting **More -&gt; Convert to RGB** in the **Channels** tool window.

![](/assets/part6/channel_tool_convert_to_rgb.jpg)

You can also convert to RGB via **Image -&gt; Color -&gt; Stack to RGB.**

![](/assets/part6/convert_to_rgb_menu.jpg)

This will create a flat RGB image of whatever is displayed in the active slice. \(RGB\) will be displayed beside the image title in the new image window.

![](/assets/part6/convert_to_rgb_result.jpg)

## Assigning or Changing Image Colours in Composites {#assigning-or-changing-image-colours-in-composites}

You can also use the Channels Tool to assign different colours to each channel in a composite image before converting to RGB.

To do this in composite mode, select the channel you wish to change using the slider at the bottom of the image. Then go to **More** and select your colour from the menu.

![](/assets/part6/channel_tool_assign_colors1.jpg)

You can also do this in colour or greyscale mode by selecting the channel using the check box or slider and repeating these steps.

![](/assets/part6/channel_tool_assign_colors2.jpg)

Colours can also be changed in composites by selecting the channel and changing the LUT using the same methods as described for monochrome images above.

You can change all channels in the image in this way \(for example to give magenta, yellow & cyan instead of red, green & blue\) and then convert to a 24bit RGB image in the same way as above to create a single merged image in the new colours.

![](/assets/part6/channel_tool_assign_colors_result.jpg)

## Merging Images/Assigning Colours with More Than 8 Channels {#merging-images-assigning-colours-with-more-than-8-channels}

There are only 8 options available when using the **Merge Channels** tool. So in order to create a merge of 8 or more colours a different method has to be used. The images that you want to colour need to be added into a stack.

Open the images you want to merge then go to **Images -&gt; Stack -&gt; Images to Stack**.

![](/assets/part6/images_to_stack_menu.jpg)

In the resulting window make sure both boxes are ticked. You can give the stack a name, or just leave it as the default name - _Stack_.

![](/assets/part6/images_to_stack_options.jpg)

Note: The images will be added into the stack in alphabetical order based on their names.

To be able to change to colour of each channel in the stack, it needs to be converted to a composite image. Go to **Image -&gt; Colour -&gt; Make Composite**.

![](/assets/part6/color_make_composite_menu.jpg)

In the options window, leave the **Display Mode** as **Composite** and press **OK**.

![](/assets/part6/color_make_composite_options.jpg)

This will create a composite stack of your channels. In this example, we only have 3 channels, but this method can be used for any number of channels.

Note: Colours will be assigned to images in the stack in the order Red-Green-Blue, if the alphabetical ordering in the stack does not match the channels, this will cause the colours to be incorrectly assigned. That’s OK – because we are doing this to change the colours anyway.

![](/assets/part6/color_make_composite_result.jpg)

You can now apply different colours to the channels in this composite stack and then create your RGB image using the methods shown above.

![](/assets/part6/color_make_composite_result_example1.jpg)

## Saturation Indicator {#saturation-indicator}

The saturation indicator or **HiLo LUT** creates an image with some pixels in red and some pixels in blue. The red and blue pixels represent intensity values at the two extremes of the range. Red pixels are fully saturated \(i.e. pure white\) and blue pixels are fully under saturated \(i.e. totally black\). Both these types of pixels contain no measurable information as you cannot be sure how far above or below saturation they are.

To check the saturation levels, select your image and go to **Image -&gt; Lookup Tables -&gt; HiLo**.

![](/assets/part6/HiLo_lookup_table_menu.jpg)

In the demonstration image here we have adjusted the image to show a high level of over- and under-saturation, as shown by the red and blue in the resulting image.

![](/assets/part6/HiLo_lookup_table_result.jpg)

## Working with Colours in IHC Images {#working-with-colours-in-ihc-images}

Immunohistochemistry images do not have individual RGB channels like fluorescence images. You can still separate out the individual colours for basic area or counting measurements however, using colour deconvolution. These separated ‘channels’ cannot be used for measurements like intensity.

To find the **Colour Devoncolution** tool go to **Image -&gt; Color -&gt; Colour Deconvolution**.

![](/assets/part6/color_deconvolution_menu.jpg)

In the colour deconvolution window, there are a number of options in the drop down menu. The first option, **From ROI**, lets you specify the different stains in your image manually. The others are preconfigured to work with most standard histological stains. Select your stain and press **OK** \(In this example we are using Masson Trichrome\).

![](/assets/part6/color_deconvolution_options.jpg)

This will separate the image into 3 ‘channels’ – in this case, each is representative of one dye used. For two colour stains such as H&E or Dab the two stains will be separated and a third image will display the mathematical leftovers from the equation used for separation.

![](/assets/part6/color_deconvolution_result.jpg)

You can now use any of these ‘channels’ for measurements like counts, or area. The methods for these are described in later sections.

You can also use these separated images to transform a histological stained image into a pseudo fluorescent image.

First you will need to invert each of the individual images. As previously described, do this for each image by selecting the image and going to **Edit -&gt; Invert** \(or using shortcut Ctrl+Shift+I\).

![](/assets/part6/color_deconvolution_invert_result.jpg)

You can then assign LUTs to each image and merge the ‘channels’ using the methods previously described.

![](/assets/part6/color_deconvolution_merge_inverted_results_1.jpg)

![](/assets/part6/color_deconvolution_merge_inverted_results_2.jpg)

This will give you a pseudo-fluorescent version of your immunohistochemistry image.

