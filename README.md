# Computer_Vision_Chessbot

Run trained neural network on tiles generated from image

Given image url to a chessboard image, display a visualization of FEN and link to a lichess analysis
Return minimum certainty for prediction.

A handful of failures, but we have greater than 98% success for 78% of screenshots, including
several out-of-left-field screenshots from mobile chess apps. Certainty is defined as the product 
of all 64 tile probabilities together, which is a bit stricter than minimum certainty, but shows
overall certainty for the board better.

Say two pieces had 90% probability of correctness (the rest are 100%), then the overall certainty 
for the board should be lower than 90%, 81% in that case.

Looking at the failure cases, it looks like the images from lichess or chess and other more common
screenshots were good, the others had a couple to several wrong pieces within. On the whole it actually 
got most of them correct, and when it didn't the certainty dropped extremely quickly. The certainty 
range does a good job of being uncertain in the cases where it failed, and 98%+ certain for 
the success cases.
