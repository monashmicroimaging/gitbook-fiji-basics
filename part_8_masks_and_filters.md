# PART 8: MASKS AND FILTERS {#part-8-masks-and-filters}

Creating thresholds and masks and applying filters forms the basis for a number of analysis methods. This section outlines the various options for masks and filters and how to apply them to your images prior to analysis.

The image **Nuclei-1** and image set ‘**RGBstackProjection, RGB-blue, RGB-green** and **RGB-red**’ are used for demonstration purposes in this section.

## Threshold Image {#threshold-image}

For a number of basic measurements an image first needs to have a threshold applied to it.

To apply a threshold, select your image and go to **Image Adjust Threshold** \(or shortcut Ctrl+Shift+T\).

![](/assets/part9/adjust_threshold_menu.jpg)

A red mask will be placed on the parts of the image that are selected by the threshold and a window will open where you can adjust the threshold on the image.

![](/assets/part8/threshold_options.jpg)

In the window that opens, ensure the box beside **Dark background** is checked. The drop down box on the left \(the one that says default\) has 16 different auto threshold algorithms to choose from. You can adjust the threshold by moving the sliders. The top slider sets the bottom range of the threshold and the bottom slider adjusts the top range of the threshold. The red box on the histogram shows which parts of the histogram are being thresholded.

![](/assets/part8/threshold_options_automatic_methods.jpg)

Select the threshold that best suits your data and adjust as needed.

![](/assets/part8/threshold_image_result.jpg)

You can also automatically test the range of threshold algorithms on your image without scrollin through the dropdown list one at a time.

To use the auto-test for thresholds, go to **Image Adjust Auto Threshold**.

![](/assets/part8/auto_threshold_menu.jpg)

In the dialog box that opens up set the **Method** to **Try All**, make sure the **White objects on black background** and **Show threshold values in log window** boxes are ticked. Press **OK**.

![](/assets/part8/auto_threshold_options.jpg)

A montage will be generated showing what each auto threshold algorithm would produce on the image. The list in the log that was created will show the order of the algorithms used in the montage.

![](/assets/part8/auto_threshold_results.jpg)

## Creating a Mask {#creating-a-mask}

If you need to convert your threshold to a mask, or binary, there are several options you can use. If you select **Apply** in the threshold window it will convert the threshold to a mask.

You can also go to **Process Binary Convert to Mask**.

![](/assets/part8/binary_mask_menu.jpg)

To generate a binary go to **Process Binary Make Binary**.

![](/assets/part8/binary_make_binary_menu.jpg)

A window will open with binary options, select your options and click **OK** to generate the binary image.

![](/assets/part8/binary_options.jpg)

![](/assets/part8/binary_mask_threshold_results.jpg)

## Making Adjustments to Masks and Binaries {#making-adjustments-to-masks-and-binaries}

Sometimes adjustments need to be made to binaries/masks before analysis to ensure it is accurately representing the data. There are a number of tools available to help you get the best fit to your data. All of these tools can be found under **Process Binary**.

![](/assets/part8/process_binary_menu.jpg)

Small gaps left in the mask after thresholding can easily be corrected for by using the **Close** tool.

![](/assets/part8/process_binary_close_operation.jpg)

Similar to this is **Fill Holes**.

![](/assets/part8/process_binary_fill_holes.jpg)

Sometimes you will need to add or remove a small layer from the edges of the mask. This could be useful for things like membrane measurements or morphology analysis.

To add or remove from the edges of a mask or binary you can use the **Dilate** or **Erode** tools. **Dilate** will add a thin layer around the edge of the existing mask. **Erode** will remove a thin layer from around the edge of the mask.

![](/assets/part8/process_binary_dilate_erode.jpg)

Sometimes separate objects in your image will be touching. When you create a mask of these they will appear as a single object. This can be a problem for some types of analysis, such as counting. But you can use the **Watershed** tool to detect and separate these objects within the mask so they can be counted as individual objects again.

![](/assets/part8/process_binary_watershed.jpg)

## Clear Inside/Outside {#clear-inside-outside}

Clear inside and outside can also be useful for adjusting your binaries before making measurements. Sometimes there can be small blemishes in your image that effect your measurements. Or you may want to focus your measurement on a single area of the image. You can crop the image to remove items before analysis, or you can use the clear functions.

Note: We strongly advise against removing objects from images before analysis and publishing of results. **Removal of any image information that can alter the outcome can be considered image manipulation.** Use these functions with care and caution.

To use the clear functions you first need to draw an ROI around the area you wish to clear, or keep.

In this example we are using cells for emphasis, but clear functions are usually applied to binaries/masks to remove blemishes or mistakes prior to analysis and we do not recommend removing cells from images in this manner.

![](/assets/part8/clear_image_BEFORE.jpg)

Once you have your ROI, go to **Edit Clear** to clear the inside of the ROI.

![](/assets/part8/clear_menu.jpg) ![](/assets/part8/clear_image_after.jpg)

Or use **Edit Clear Outside**, to clear the rest of the image outside the ROI.

![](/assets/part8/clear_outside_menu.jpg) ![](/assets/part8/clear_outside_result.jpg)

## Image Calculator {#image-calculator}

Image calculator is another way to select for specific areas where you want to apply your analysis. Image calculator performs arithmetic operations between two images. These can be your original images or stacks, an image/stack and a mask or two masks.

The **Image Calculator** can be found under **Process Image Calculator**.

![](/assets/part8/image_calculator_menu.jpg)

In the resulting window you can select image 1 and image 2 from the drop down menus and choose your operation from the list in the middle. Check the box next to **Create new window** to generate the calculation as a new image, otherwise it will override image 1.

![](/assets/part8/image_calculator_options.jpg)

In the image calculator **Add** creates a new image with the pixels from image 1 added to the pixels from image 2. This is demonstrated below, combining two images into a single image for measurements.

![](/assets/part8/image_calculator_addition_example1.jpg)

**Subtract** will remove the pixels in image 2 from image 1. This is demonstrated below with two masks of the same image. The mask in image 2 has been eroded and will be subtracted from the original to leave only the edge of the nuclei for analysis.

![](/assets/part8/image_calculator_subtraction_example1.jpg)

You can also use a mask to subtract an area of an image prior to analysis. For example we use the mask of the nucleus here to subtract pixels from the green channel so only cytoplasmic signal remains for analysis.

![](/assets/part8/image_calculator_subtraction_example2_input_images.jpg)

![](/assets/part8/image_calculator_subtraction_example2_result.jpg)

Image calculators can be useful in a number of different analysis techniques. Although not all examples can be shown here, they are worth taking some time to explore as a part of your image analysis.

## Find Edges and Find Maxima {#find-edges-and-find-maxima}

The **Find Edges** and **Find Maxima** tools can help you segment your images. Both of these tools can be found under the **Process** menu.

![](/assets/part8/find_edges_find_maxima_menu.jpg)

To segment the edges of your image, select the image and then select **Find Edges**. FIJI will ‘outline’ the edges of the signal in your image.

![](/assets/part8/find_edges_result.jpg)

You can then threshold this image to select edges of the signal only.

![](/assets/part8/find_edges_threshold_result.jpg)

Once you are happy with the threshold, click **Apply** or create a mask or binary as previously shown.

![](/assets/part8/find_edges_threshold_mask.jpg)

**Find Maxima** is particularly helpful for segmenting images of dense cell populations or objects.

Select your image and the go to **Find Maxima**. A window will open with options for the selection.

Select the box next to **Preview point selection** to see the default settings. These default settings will create a dense selection. Ensure **Exclude edge maxima** is selected.

![](/assets/part8/find_maxima_options_1.jpg)

Increase the **Noise tolerance** to show reduce the point selection range on the image. For segmentation, 1 point per cell is ideal. In this example, a noise tolerance of 1200 is needed to best select the data. For segmentation, select **Segmented Particles** from the drop down list under **Output type**.

![](/assets/part8/find_maxima_options_2.jpg)

When you are happy with your selection click **OK** to generate a segmented image mask.

![](/assets/part8/find_maxima_segmentation_result.jpg)

This mask can be used in combination with cell stains to segment and measure individual cells.

## Image Filters {#image-filters}

Filters can be used to “smooth” your images before analysis. These are another helpful tool for removing blemishes or ensuring that your mask fits the data well before analysis.

You can find some filters directly under the **Process** menu. Others are found under **Process Filters** or **Process Noise**.

The different filters are demonstrated below with before and after images

Smooth:

Sharpen:

Despeckle:

Despeckle \(mask\):

Remove Outliers:

In this filter, you need to specify the outlier radius in pixels, and threshold. Select the checkbox next to **Preview** to see the changes before you apply them to the image. Click **OK** when you are happy with your changes.

Median:

Again, in this filter, you need to specify the radius in pixels. Select the checkbox next to **Preview** to see the changes before you apply them to the image. Click **OK** when you are happy with your changes.

Gausian Blur:

This filter uses convolution to produce a smoothing effect. Here you again, need to specify the radius. Select the checkbox next to **Preview** to see the changes before you apply them and click **OK** when you want to apply changes to the image.

Note: As with a lot of functions used to aid analysis, filters should be used with care and caution so as to not manipulate the outcome of the data. Filters should only be applied to allow the best fit to the image and not to force the image to fit a preconceived idea.

