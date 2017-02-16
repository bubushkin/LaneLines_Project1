Lane Lines - Project 1:

Pipeline:
  My pipeline consist of following:

  **Please note that I am only describing the flow of functions/methods I have implemented/modified**


    1. Dynamically drawing trapezoid based on frame size as a region of interest.
        Trapezoid points are defined as following:
        
          1. (5th percent of the x axis, 100th % y axis) 
          
          2. (33th percent of x axis, 62nd percent of y axis) 
          
          3. (63rd percent of x axis, 62nd percent of y axis)
          
          4. (95th percent of x axis, 100th percent of y axis)
          
    2.  Color filter. In color_filter function I am transforming my frame into "binary" to seprate out YELLOW and WHITE colors.
        I am using one single range for both colors YELLOW and WHITE (see params hashmap in code);
        'low_color_threshold': np.array([0, 140, 200], dtype = "uint8"),
        'high_color_threshold': np.array([255, 255, 255], dtype = "uint8")
        
    3. Grayscale (Provided)
    4. Gaussian Blur (Provided)
    5. Canny (Provided).
    6. Retrieve region of interest by applying the trapezoid.
    7. Hough Transformation (Provided). In hough_transform I am supplying one additional parameter trapezoid length for draw_lines function.
    8. Drawing lane lines. I opted out from distinguishing right/left slopes. Instead I seperate left and right points into arrays and use linear regression to get the line parameters (scipy.stats.linregress). 
    After that I identify the max y-point for the lines to draw from the "polygon" I passed earlier. 
    In the end I identify my left and right x values and draw the lines accordingly. 
      
Result:
    ![Alt text](https://github.com/bubushkin/LaneLines_Project1/blob/master/resources/images/results/outputSolidWhiteRight.png "solidWhiteRight")
    ![Alt text](https://github.com/bubushkin/LaneLines_Project1/blob/master/resources/images/results/outputSolidYellowLeft.png "solidYellowLeft")

Improvements:
    An improvement I could make is to seperate out ranges for YELLOW and WHITE colors and make the range shorter. Instead of processing them as a single unit. My current design breaks on challange video when Car passes concrete road where YELLOW and WHITE are difficult to identify. 
