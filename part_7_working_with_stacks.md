# PART 7: WORKING WITH STACKS {#part-7-working-with-stacks}

Image stacks are a number of related images opened on top of each other in a single window. Stacks can represent different channels from the same image, z-slices captured on the microscope or time series. When channel, Z-series or time information is recorded the images are usually opened as stacks automatically when bio-formats importer is used to open the files. You can also generate a stack yourself from related TIFF or JPEG images.

This section goes through the tools and methods for working with image stacks.

The image **NeuralTube** and image stacks **RGBStack**, **3D-1**, **MovieStack** and **HyperStack** will be used for demonstration throughout this section.

## Navigating Stacks {#navigating-stacks}

You can easily move through the slices in a stack using the bar at the bottom of the image.

**2 3**

**1**

**4**

Click and drag the slider (1) to move through the stacks. You can also click on the left (2) and right (3) arrows to move the stack by 1 slice or click the play button (4) to run through the stack slices automatically.

You can monitor the slice number in the image information at the top left of the image window.

## Creating and Dismantling Stacks {#creating-and-dismantling-stacks}

To create a stack from multiple individual images go to **Image Stacks Images to Stack.**

An options window will open. You can give the stack a new name, or keep the generic ‘Stack’. To keep the original images select the box next to **Keep Source Images**.

Click **OK** to generate the stack.

To reverse this and generate multiple single images from a stack go to **Image Stacks Stack to Images**

## Altering Stack Slices {#altering-stack-slices}

You can alter the slices in a stack by adding, deleting or rearranging them.

To add or delete slices from a stack, navigate to the slice you want to modify and go to **Image Stacks**, and select the desired option.

Selecting add slice will insert a new blank/black slice into the current stack position. Selecting delete slice will remove the current slice from the stack.

You can also add and delete multiple slices using the **Slice Keeper** or **Slice Remover** tools. To find these go to **Image Stacks Tools**.

**Slice Keeper** will ask you to nominate the slices you wish to keep in the stack, by number. You can also use **Increment** to keep every 2nd, 3rd, 4th, etc slice from the stack. Enter your numbers and select **OK** to generate the new stack.

**Slice Remover** will prompt you to nominate the slices you wish to remove from the stack, by number. As with slice keeper, you can also use **Increment** to remove every 2nd, 3rd, 4th, etc slice from the stack. Enter your numbers and select **OK** to generate the new stack.

You can also rearrange the order of slices in a stack using the **Stack Sorter** tool. Go to **Image Stacks Tools Stack Sorter.**

You can then move a slice forwards or backwards using the arrows (1) in the options box.

You can also select **First** (2) or **Last** (3) to move the current slice to the front or back of the stack.

Other options include duplicating a slice (4) or inserting a new image into the stack from a file (5).

All of these commands will act on the current slice in the stack. Always scroll to the slice you want to change before selecting an option.

You can also select **Reverse** (6) to reverse the order of the entire stack.

## Split and Concatenate Stacks {#split-and-concatenate-stacks}

You can split a stack into smaller parts by selecting **Image Stacks Tools Stack Splitter**

Enter the number of smaller stacks you wish to split into and select **OK**.

Note: The smaller stacks must be of equal size, so you need to enter a number divisible by the total number of slices. This allows the stack to split into multiple equal parts.

To combine multiple small stacks into one select **Image Stacks Tools Concatenate.**

In the resulting **Concatenator** window, ensure the smaller stacks are in the correct order by selecting from the drop down menus. You can give the new stack a name or keep the generic ‘Concatenated Stacks’ and check the box next to **Keep original images** if you wish to keep the smaller stacks open.

Then select **OK** to generate the combined stack.

## Make Montage {#make-montage}

You can use image stacks to generate side by side montages of channels, time points or z-sections. Select your stack then go to **Image Stacks Make Montage**

A window will open with a number of options for generating the montage, including the number of columns (1) and rows (2) that you want in the montage, scaling of the image (3), which slices of your stack you want to include (4), if you want to use increments (5) and border width (6).

You can also select the check box to label the montage with the slice titles (7).

Input your required options and select **OK** to create the montage.

In the example below we have generated a montage of the individual channels and merged image using the settings shown in the options window above, but the same principles can be applied to create a montage of times or z-slices as well.

## Maximum Intensity Projections {#maximum-intensity-projections}

To create a maximum intensity projection of a confocal z-stack, open your stack and go to **Image Stacks Z-Project**.

In the **ZProjection** window enter the first and last slice you want to project and the type of projection, in this case ‘Maximum Intensity’, then select **OK** to create the projection.

A new window will open with the projected, single plane image. The new image will have the default name ‘MAX__imagename_’. You can rename this when saving by using the **Save As** function.

## 3D Projections {#3d-projections}

When working with z-stacks, you can create a 3D projection of the stack by going to **Image Stacks 3D Project**.

For most 3D projections you can leave the settings in the **3D Projection** window as default.

If you check the box next to **Interpolate**, FIJI will guess at the image information between slices. While this helps to create a smooth projection it is adding information that is not in the original image. For quantitation this should be avoided, for presentation of your 3D projection you can use it.

If the image is calibrated the **Slice spacing** should be populated correctly from the metadata. Note that this uses the z-step size, not the m/px calibration size.

Select **OK** to create the projection.

The resulting projection will have a slider at the bottom (similar to a stack) which you can use to rotate the 3D image.

## Orthogonal Views {#orthogonal-views}

An orthogonal projection is a view created in the YZ or XZ dimension of an image stack. An orthogonal projection allows you to visualise depth information one slice at a time in your sample.

To generate orthogonal slices select your z-stack and go to **Image Stack Orthogonal View** (or use shortcut Ctrl+Shift+H).

Two windows will open to the right of and below the original stack. These windows show the orthogonal projections in YZ and XZ respectively.

To change the view seen in each window, move the yellow cross hair in the original stack and scroll through the stack to change plans as usual. Each of these projections can be saved for use later.

## Reslice Z {#reslice-z}

The orthogonal projection only lets you see one slice at a time and it has the overlay lines in the way. Sometimes it can be useful to generate a stack of orthogonal slices instead. This is easily achieved by reslicing the stack along a different axis.

To generate an orthogonal stack go to **Image Stacks Reslice**.

In the window that opens you can set how the stack should be resliced (top, bottom, left, right) from the drop down menu and, if not already calibrated, set the distance between slices.

There is a tick box to select that says **Avoid Interpolation**. This should usually be ticked. As with the 3D projection, while interpolation will make the end result look better, it does this by adding extra data that wasn’t in the original image.

Select **OK** to generate the resliced stack.

The program will then ‘scan’ through the image from the selected direction and generate the new stack.

## Times Series and Saving Movies {#times-series-and-saving-movies}

Time series will also open as a stack that you can work with in a similar manner to colour or z-series stacks.

Here, the slider or play button move through the time points, rather than the channels or z-slices.

You can save your time series as a movie using FIJI by selecting **File Save As**, and choosing **AVI**

as the file type.

A window with saving options will open, which will allow you to set specific aspects of the movie.

Where possible you should create your movie without compression. The frame rate will be dependent on your images and time interval. Sometimes a trial an error of different frame rates will be needed to generate a movie that plays at an appropriate speed. Generally, something around 8 frames per second (fps) is a good starting point.

Click **OK** to create and save the movie.

The movie will not open and play automatically. You can open and play the movie file in programs QuickTime, Windows media Player or VCL Media Player to check the frame rate.

Before saving your movie you can also include add a time stamp using FIJI. To add a time stamp, select your time series stack and go to **Image Stack Time Stamper**.

In the **Time Stamper** window you will need to enter the interval between images and the format you want the time stamp to be in. You can also specify the location in pixels.

In this example, the time interval is 5mins. Time needs to be entered in seconds in the options, so you would need to put ‘300’ into the interval box. Pixels for an approximate location can be found by hovering the mouse over the area of the image you wish to use. Pixel co-ordinates will be displayed in the information bar.

You can also choose to include a suffix (sec, min, etc) or use the time format ‘00:00’.

Select **OK** to insert the time stamp into the stack. The timer will automatically run as you scroll through the stack.

You can now save your time series as a movie, using the same method as above, and the time stamp will remain embedded.

## Hyperstacks {#hyperstacks}

Often images will be captured with a 4th or 5th dimension; that is they will have a combination of multiple channels, z-sections and time. For these images the data will be presented as a hyperstack.

Each stack is presented independently with its own navigation bar, within a single window.

You can scroll through each dimension independently, you can also use the same tools to alter and navigate the stack as above (ie: delete slice), but you will be asked which dimension you want to alter.

You can also use hyperstack tools to reduce dimensionality. To find these go to **Image Hyperstack**.

**Hyperstack to Stack** will combine all dimensions into a single stack with c*z*t frames (ie; here 61 z- planes * 25 time points = 1525 frames).

**Reduce Dimensionality** will allow you to pick one dimension to remove or keep in the hyperstack.

For example you can select time only (by un-checking the box beside 61 slices) and a single stack of all time points at the current z-plane will be generated.