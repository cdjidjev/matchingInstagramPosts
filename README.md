# matchingInstagramPosts

This project analyzes Instagram comments to identify possible changed usernames within posts. 

## Data

The data files used in this analysis come from a 2015 paper titled "Analyzing labeled cyberbullying incidents on the Instagram social network" by Hosseinmardi et al. The data contains Instagram posts and comments extracted through the API.

There are 3 data files:

- labeled_0plus_to_10__full.csv
- labeled_10plus_to_40_full.csv 
- labeled_40plus_full.csv

## Analysis 

The Jupyter notebook `matchingUsernames.ipynb` reads in the 3 CSV files, merges them into a single DataFrame, and processes the data into a list of posts/sessions and associated comments.

It then loops through this list to:

- Extract all usernames (post authors and commenters)
- Check each mentioned username against previous ones 
- If no match, calculate similarity using edit distance
- Above a threshold, replace with closest matching name 

This allows finding changed usernames in the comments.

## Results

The analysis outputs metrics for:

- Number of matching usernames  
- Number of changed usernames
- Number of completely missing usernames

## Usage 

The Jupyter notebook requires Python 3 and the following libraries:

- Pandas 
- Regex
- Difflib

To run the analysis:

1. Download or clone this repo
2. Save the 3 data CSV files into the `data/` folder
3. Run the `matchingUsernames.ipynb` Jupyter notebook

Some sample output is provided in the notebook. Modify the similarity threshold or run over additional Instagram data to experiment further.
