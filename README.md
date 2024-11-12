Fuzzy-AHP for landfill site selection in R


Criteria weighting:

The F-AHP technique was initially applied to determine the weights of each criterion and rank the alternatives in R 3.5.0. The process involves the installation  and loading of the required packages for Fuzzy AHP  using the command, install.packages("fuzzyAHP") and library(fuzzyAHP). This if followed by conducting pairwise comparisons among criteria, applying fuzzy numbers to capture the uncertainty in judgments and calculating the priority vectors for each criterion using fuzzy geometric mean. The first part of the code constructs a pairwise comparison matrix, which is essential for evaluating the relative importance of various criteria involved in landfill site selection. The comparisonMatrix is created using the matrix() function, where each entry represents the relative importance of one criterion over another. The values are expressed in terms of Saaty's scale.
The FuzzyAHP library is loaded to access functions for fuzzy AHP calculations. The pairwiseComparisonMatrix() function converts the input matrix into a suitable format for further calculations. The consistency of the judgments is evaluated using the consistencyRatio() function. A CR value below 0.10 indicates acceptable consistency. The calculateWeights() function computes the weights of each criterion based on the pairwise comparison matrix. These weights reflect their relative importance in the decision-making process.

Landfill suitability maps in GIS:

Using GIS, the weighted criteria layers are combined to create a suitability map for potential landfill sites. This involves overlaying the raster layers and applying a weighted sum approach to identify areas that meet the specified thresholds for suitability.  Among the sites situated within the category of the “most suitable” index,  sites that had an area of =>15ha and fulfill the requirements in Bulawayo, were selected for further analysis.  These candidate sites were extracted and assigned Alphabetical letters. These sites were checked on the satellite images (2023) of the Bulawayo to make sure that these sites were suitable for landfill.  The centroid of each polygon was created and values were extracted for each criteria. The extracted value are ranked to create a decision matrix for alternatives and criteria. 

Ranking alternatives:

Next, a fuzzy comparison matrix is created based on predefined values representing expert judgments. The fuzzy AHP results are calculated using the fuzzy comparison matrix and values. The results are defuzzified using the Yager method to obtain crisp scores from fuzzy numbers. Finally, alternatives are ranked based on defuzzified results.
