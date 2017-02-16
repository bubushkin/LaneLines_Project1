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
    8. Drawing lane lines. In draw_lines function I am using 0(zero) as my threshold for distuingishing between left and right slope.  
    
    
    
      
Result:

Improvements:
