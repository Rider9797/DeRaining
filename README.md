**Wiener Filtering**

  1. The code takes the rainy image and its mask as input and generates a rainy_only image using the mask which contains only the rains streaks from the original rainy image.     
   3. The function estimate_blur_parameters() then calculates the length and angle of the rain streak. If there is more than one rain streak, I believe it just calculates it for the biggest rain streak. It calculates the wrong parameters as far as I know.
   4. The function motion_blur_kernel() takes the length and angle to make the blur kernel, which just models the rain streak in a straight line. You will see in the code that I have hardcoded these parameters which is how I got the results that I showed you guys previously.
   5. This blur kernel is then put into the following formula. To the best of my knowledge, this is the same closed form solution that sir was talking about, which is the formula for weiner filtering which was written in the book as well. This formula performs deconvolution.


Possible Causes of the Bad Results:
- Rain masks are not pixel perfect
- The blur kernel generated is a straight line with constant thickness, our rain streaks are not really straight lines. Some are curved and they have varying thickness.
- There might a fault int the deconvolution logic/formula.
  
