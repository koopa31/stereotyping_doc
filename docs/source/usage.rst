Usage
=====

This plugin allows you to generate a reference frame in an image of an embryo using a series of user-defined points.
Below are the steps to use the plugin along with illustrative screenshots.

Steps to Generate a Reference Frame
-----------------------------------

1. **Set resolution and cone height**

   - Set the microscope resolution (dx, dy, dz) in µm.
   - Set the cone height. By default, we chose 75 µm as it is half the telencephalon height for a zebrafish.

2. **Image Selection**

   - Set the image selection parameters to filter and load the correct images. We assume each channel has been saved in a separate tiff file:
       - **Sample identifier**: Used to filter images that belong to the same sample (default: `_s`).
       - **Number of colors**: Define the number of colors used in your images (default: `2`).
       - **Identifiers for the color channels**:
          - **Blue channel**: Define the identifier for blue channel images (default: `CSU-405 Em 440-460`).
          - **Green channel**: Define the identifier for green channel images (default: `CSU-488 Em 510-540`).
          - **Red channel**: Define the identifier for red channel images (default: `CSU-561 Em 593LP`).

3. **Select the Folder Containing Images**

   - Open Napari and launch the plugin.
   - Click on the "Select Folder" button to choose the folder containing your embryo images. Images must be 3D and can be composed of several channels.

   .. figure:: https://raw.githubusercontent.com/koopa31/stereotyping_doc/main/docs/images/select_folder.gif?raw=true
      :alt: GIF

4. **Place the Points in the Image**

   - For each image, place eight points in the following order (the instructions to place the points are detailed in the plugin interface):

     1. The summit of the cone.
     2. The first point to define the telencephalon plane.
     3. The second point to define the telencephalon plane.
     4. The third point to define the telencephalon plane.
     5. The fourth point to define the telencephalon plane.
     6. The top of the embryo (back part).
     7. The bottom of the embryo (ventral part).
     8. A point on the cone base.

   .. figure:: https://raw.githubusercontent.com/koopa31/stereotyping_doc/main/docs/images/placer_points.gif?raw=true
      :alt: GIF

   Once all eight points are placed, click on the "Calculate Coordinates" button to compute the reference frame.

5. **Calculate the Coordinates of a given point in the new reference frame (optional)**

   - You can show the axes, the telencephalon plane and the cone by ticking the corresponding cases. If so, one can click on
     *compute coordinates in the new reference frame*. You will be asked to set a point and its position in the new reference frame will be
     saved and displayed in the terminal. If you decide not to display the result, the next image in the
     folder will be loaded and the reference frame parameters saved automatically (see next section).

   .. figure:: https://raw.githubusercontent.com/koopa31/stereotyping_doc/main/docs/images/coords.gif?raw=true
      :alt: GIF

6. **Save the Results**

   - The plugin will save the coordinates of the point placed in **4.** (not mandatory) and the reference frame parameters in a CSV file
     named as the corresponding image.


Notes
-----

- Ensure that you place the points accurately to get a reliable reference frame.
- The plugin supports various image formats including `.png`, `.TIF`, `.tif`, and `.tiff`.


