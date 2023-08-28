# deep-learning-challenge
module 21 challenge for UMN data bootcamp 2023 by Ryan Cornelius.

primary file is 'Deep_Learning_Challenge.ipynb' and output model in 'Model_RC_Chlng21.h5'


Module 21 report:

Overview
This analysis looked at a dataset of venture capital applicants. The goal is to create an model than can take concrete data about the applicant such as the affiliation, classification, use case, organization, income, and desired capital and accurately determine the likelyhood of the applicant's success and a return on investment. 

Results
Data Processing
	* The target is the "is successful" label of the dataset. The applicant needs to be successful for the venture to be worthwhile.
	* The features are the remaining terms mentioned earlier: the affiliation, classification, use case, organization, income, and desired capital
	* The remaining columns are then the EIN and name columns, which are simply descriptors of the organizations. 

Compiling, training, and evaluation
	* My model ended up being comprised of 4 hidden layers with 2080, 512, 64, and 8 nodes respectively. I used relu activation for all of the hidden layers and a sigmoid activation for the output layer. I tested switching to tanh activation functions within the output and hidden layers, but saw little to no change. What actually appeared the most "efficient" was having about 2x the number of terms as nodes per layer. However, I also wanted to test how many terms I could add without bogging down computation time dramatically, especially since I got GPU compute working locally, and tested it outside of Google Colab. Around 500 nodes were required before epoch times notably increased from 1ms/step. From here I increased the epochs and the nodes/layers to a reasonable training duration. 
	* In the end, I was not able to achieve the target performance. I wanted to achieve the performance via increasing model complexity instead of adjusting parameters directly (to my own folly). 
	* Increase Epochs
	* Increase hidden layers
	* Adjusted activation functions to tanh (and back)
	* Adjusted cut-off values for the data bins. 
	
Summary
Overall, I achieved an accuracy of 0.7433, and I am somewhat satisfied with that value. I wouldn't recommend this specific model however, as I believe the capital utilization may still be more effectively determined by human values. I believe that a neural network is still likely to be a good model choice for the dataset however, as it should be able to correlate the inputs to trends more effectively that a purely math-based fit model.

