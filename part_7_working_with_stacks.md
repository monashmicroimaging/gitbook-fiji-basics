# PART 7: WORKING WITH STACKS {#part-7-working-with-stacks}

Image stacks are a number of related images opened on top of each other in a single window. Stacks can represent different channels from the same image, z-slices captured on the microscope or time series. When channel, Z-series or time information is recorded the images are usually opened as stacks automatically when bio-formats importer is used to open the files. You can also generate a stack yourself from related TIFF or JPEG images.

This section goes through the tools and methods for working with image stacks.

The image **NeuralTube** and image stacks **RGBStack**, **3D-1**, **MovieStack** and **HyperStack** will be used for demonstration throughout this section.

## Navigating Stacks {#navigating-stacks}

You can easily move through the slices in a stack using the bar at the bottom of the image.

![](/assets/part7/stacks_navigation_slider.jpg)

Click and drag the slider \(1\) to move through the stacks. You can also click on the left \(2\) and right \(3\) arrows to move the stack by 1 slice or click the play button \(4\) to run through the stack slices automatically.

You can monitor the slice number in the image information at the top left of the image window.

![](/assets/part7/stacks_information.jpg)

## Creating and Dismantling Stacks {#creating-and-dismantling-stacks}

To create a stack from multiple individual images go to **Image -&gt; Stacks -&gt; Images to Stack.**

![](/assets/part7/images_to_stack_menu.jpg)

An options window will open. You can give the stack a new name, or keep the generic ‘Stack’. To keep the original images select the box next to **Keep Source Images**.

![](/assets/part7/images_to_stack_options.jpg)

Click **OK** to generate the stack.

![](/assets/part7/images_to_stack_result.jpg)

To reverse this and generate multiple single images from a stack go to **Image -&gt; Stacks -&gt; Stack to Images.**

## Altering Stack Slices {#altering-stack-slices}

You can alter the slices in a stack by adding, deleting or rearranging them.

To add or delete slices from a stack, navigate to the slice you want to modify and go to **Image -&gt; Stacks**, and select the desired option.

![](/assets/part7/add_slice_menu.jpg)

Selecting add slice will insert a new blank/black slice into the current stack position. Selecting delete slice will remove the current slice from the stack.

You can also add and delete multiple slices using the **Slice Keeper** or **Slice Remover** tools. To find these go to **Image -&gt; Stacks -&gt; Tools**.

![](/assets/part7/slice_keeper_menu.jpg) ![](/assets/part7/slice_remover_menu.jpg)

**Slice Keeper** will ask you to nominate the slices you wish to keep in the stack, by number. You can also use **Increment** to keep every 2nd, 3rd, 4th, etc slice from the stack. Enter your numbers and select **OK** to generate the new stack.

![](/assets/part7/slice_keeper_options.jpg)

**Slice Remover** will prompt you to nominate the slices you wish to remove from the stack, by number. As with slice keeper, you can also use **Increment** to remove every 2nd, 3rd, 4th, etc slice from the stack. Enter your numbers and select **OK** to generate the new stack.

![](/assets/part7/slice_remover_options.jpg)

You can also rearrange the order of slices in a stack using the **Stack Sorter** tool. Go to **Image -&gt; Stacks -&gt; Tools -&gt; Stack Sorter.**

![](/assets/part7/stack_sorter_menu.jpg) ![](/assets/part7/stack_sorter_options.jpg)

You can then move a slice forwards or backwards using the arrows \(1\) in the options box.

You can also select **First** \(2\) or **Last** \(3\) to move the current slice to the front or back of the stack.

Other options include duplicating a slice \(4\) or inserting a new image into the stack from a file \(5\).

All of these commands will act on the current slice in the stack. Always scroll to the slice you want to change before selecting an option.

You can also select **Reverse** \(6\) to reverse the order of the entire stack.

## Split and Concatenate Stacks {#split-and-concatenate-stacks}

You can split a stack into smaller parts by selecting **Image -&gt; Stacks -&gt; Tools -&gt; Stack Splitter.**

![](/assets/part7/stack_splitter_menu.jpg)

Enter the number of smaller stacks you wish to split into and select **OK**.

![](/assets/part7/stack_splitter_options.jpg)

Note: The smaller stacks must be of equal size, so you need to enter a number divisible by the total number of slices. This allows the stack to split into multiple equal parts.

![](/assets/part7/stack_splitter_result.jpg)

To combine multiple small stacks into one select **Image -&gt; Stacks -&gt; Tools -&gt; Concatenate.**

![](/assets/part7/concatenate_stacks_menu.jpg)

In the resulting **Concatenator** window, ensure the smaller stacks are in the correct order by selecting from the drop down menus. You can give the new stack a name or keep the generic ‘Concatenated Stacks’ and check the box next to **Keep original images** if you wish to keep the smaller stacks open.

![](/assets/part7/concatenate_stacks_options.jpg)

Then select **OK** to generate the combined stack.

## Make Montage {#make-montage}

You can use image stacks to generate side by side montages of channels, time points or z-sections. Select your stack then go to **Image -&gt; Stacks -&gt; Make Montage.**

![](/assets/part7/montage_menu.jpg)

![](/assets/part7/montage_options.jpg)

A window will open with a number of options for generating the montage, including the number of columns \(1\) and rows \(2\) that you want in the montage, scaling of the image \(3\), which slices of your stack you want to include \(4\), if you want to use increments \(5\) and border width \(6\).

You can also select the check box to label the montage with the slice titles \(7\).

Input your required options and select **OK** to create the montage.

In the example below we have generated a montage of the individual channels and merged image using the settings shown in the options window above, but the same principles can be applied to create a montage of times or z-slices as well.

![](/assets/part7/montage_result.jpg)

## Maximum Intensity Projections {#maximum-intensity-projections}

To create a maximum intensity projection of a confocal z-stack, open your stack and go to **Image -&gt; Stacks -&gt; Z-Project.**

![](/assets/part7/z_project_menu.jpg)

In the **ZProjection** window enter the first and last slice you want to project and the type of projection, in this case ‘Maximum Intensity’, then select **OK** to create the projection.

![](/assets/part7/z_project_options.jpg)

A new window will open with the projected, single plane image. The new image will have the default name ‘MAX_\_imagename_’. You can rename this when saving by using the **Save As** function.

![](/assets/part7/z_project_result.jpg)

## 3D Projections {#3d-projections}

When working with z-stacks, you can create a 3D projection of the stack by going to **Image -&gt; Stacks -&gt; 3D Project**.

![](/assets/part7/3d_project_menu.jpg)

For most 3D projections you can leave the settings in the **3D Projection** window as default.

If you check the box next to **Interpolate**, FIJI will guess at the image information between slices. While this helps to create a smooth projection it is adding information that is not in the original image. For quantitation this should be avoided, for presentation of your 3D projection you can use it.

If the image is calibrated the **Slice spacing** should be populated correctly from the metadata. Note that this uses the z-step size, not the m/px calibration size.

![](/assets/part7/3d_project_options.jpg)

Select **OK** to create the projection.

The resulting projection will have a slider at the bottom \(similar to a stack\) which you can use to rotate the 3D image.

![](/assets/part7/3d_project_result.jpg)

## Orthogonal Views {#orthogonal-views}

An orthogonal projection is a view created in the YZ or XZ dimension of an image stack. An orthogonal projection allows you to visualise depth information one slice at a time in your sample.

To generate orthogonal slices select your z-stack and go to **Image -&gt; Stack -&gt; Orthogonal View** \(or use shortcut Ctrl+Shift+H\).

![](/assets/part7/orthogonal_views_menu.jpg)

Two windows will open to the right of and below the original stack. These windows show the orthogonal projections in YZ and XZ respectively.

![](/assets/part7/orthogonal_views_window.jpg)

To change the view seen in each window, move the yellow cross hair in the original stack and scroll through the stack to change plans as usual. Each of these projections can be saved for use later.

## Reslice Z {#reslice-z}

The orthogonal projection only lets you see one slice at a time and it has the overlay lines in the way. Sometimes it can be useful to generate a stack of orthogonal slices instead. This is easily achieved by reslicing the stack along a different axis.

To generate an orthogonal stack go to **Image -&gt; Stacks -&gt; Reslice.**

![](/assets/part7/reslice_menu.jpg)

In the window that opens you can set how the stack should be resliced \(top, bottom, left, right\) from the drop down menu and, if not already calibrated, set the distance between slices.

There is a tick box to select that says **Avoid Interpolation**. This should usually be ticked. As with the 3D projection, while interpolation will make the end result look better, it does this by adding extra data that wasn’t in the original image.

Select **OK** to generate the resliced stack.

![](/assets/part7/reslice_options.jpg)

The program will then ‘scan’ through the image from the selected direction and generate the new stack.

![](/assets/part7/reslice_result.jpg)

## Times Series and Saving Movies {#times-series-and-saving-movies}

Time series will also open as a stack that you can work with in a similar manner to colour or z-series stacks.

![](/assets/part7/time_series.jpg)

Here, the slider or play button move through the time points, rather than the channels or z-slices.

You can save your time series as a movie using FIJI by selecting **File -&gt; Save As**, and choosing **AVI **as the file type.

![](/assets/part7/save_movie_menu.jpg)

A window with saving options will open, which will allow you to set specific aspects of the movie.

![](/assets/part7/save_movie_options.jpg)

Where possible you should create your movie without compression. The frame rate will be dependent on your images and time interval. Sometimes a trial an error of different frame rates will be needed to generate a movie that plays at an appropriate speed. Generally, something around 8 frames per second \(fps\) is a good starting point.

![](/assets/part7/save_movie_8fps.jpg)

Click **OK** to create and save the movie.

The movie will not open and play automatically. You can open and play the movie file in programs QuickTime, Windows media Player or VCL Media Player to check the frame rate.

![](/assets/part7/save_movie_file_icon.jpg)

![](/assets/part7/save_movie_result.jpg)

Before saving your movie you can also include add a time stamp using FIJI. To add a time stamp, select your time series stack and go to **Image -&gt; Stack -&gt; Time Stamper**.

![](/assets/part7/time_stamp_menu.jpg)

In the **Time Stamper** window you will need to enter the interval between images and the format you want the time stamp to be in. You can also specify the location in pixels.

In this example, the time interval is 5mins. Time needs to be entered in seconds in the options, so you would need to put ‘300’ into the interval box. Pixels for an approximate location can be found by hovering the mouse over the area of the image you wish to use. Pixel co-ordinates will be displayed in the information bar.

You can also choose to include a suffix \(sec, min, etc\) or use the time format ‘00:00’.

![](/assets/part7/time_stamp_options.jpg)

Select **OK** to insert the time stamp into the stack. The timer will automatically run as you scroll through the stack.

![](/assets/part7/time_stamp_result.jpg)

You can now save your time series as a movie, using the same method as above, and the time stamp will remain embedded.

## Hyperstacks {#hyperstacks}

Often images will be captured with a 4th or 5th dimension; that is they will have a combination of multiple channels, z-sections and time. For these images the data will be presented as a hyperstack.

Each stack is presented independently with its own navigation bar, within a single window.

![](/assets/part7/hyperstack.jpg)

You can scroll through each dimension independently, you can also use the same tools to alter and navigate the stack as above \(ie: delete slice\), but you will be asked which dimension you want to alter.

![](/assets/part7/hyperstack_delete.jpg)

You can also use hyperstack tools to reduce dimensionality. To find these go to **Image -&gt; Hyperstack**.

![](/assets/part7/myperstack_menu.jpg)

**Hyperstack to Stack** will combine all dimensions into a single stack with c\_z\_t frames \(ie; here 61 z- planes \* 25 time points = 1525 frames\).

![](/assets/part7/hyperstack_to_stack.jpg)

**Reduce Dimensionality** will allow you to pick one dimension to remove or keep in the hyperstack.

![](/assets/part7/hyperstack_reduce_dimensionality.jpg)

For example you can select time only \(by un-checking the box beside 61 slices\) and a single stack of all time points at the current z-plane will be generated.

![](/assets/part7/hyperstack_reduce_dimensionality_result.jpg)

