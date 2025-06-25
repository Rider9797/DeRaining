**Wiener Filtering**

  1. The code takes the rainy image and its mask as input and generates a rainy_only image using the mask which contains only the rains streaks from the original rainy image.
   2. The function estimate_blur_parameters() then calculates the length and angle of the rain streak. If there is more than one rain streak, I believe it just calculates it for the biggest rain streak. It calculates the wrong parameters as far as I know.
   3. The function motion_blur_kernel() takes the length and angle to make the blur kernel, which just models the rain streak in a straight line.
   4. This blur kernel is then put into the following formula. To the best of my knowledge, this is the same closed form solution that sir was talking about, which is the formula for weiner filtering which was written in the book as well.
  
