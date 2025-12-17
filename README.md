# Project: Movie Recommender System Using Machine Learning!
Recommendation systems are becoming increasingly important in today’s extremely busy world. People are always short on time with the myriad tasks they need to accomplish in the limited 24 hours. Therefore, the recommendation systems are important as they help them make the right choices, without having to expend their cognitive resources.

The purpose of a recommendation system basically is to search for content that would be interesting to an individual. Moreover, it involves a number of factors to create personalised lists of useful and interesting content specific to each user/individual. Recommendation systems are Artificial Intelligence based algorithms that skim through all possible options and create a customized list of items that are interesting and relevant to an individual. These results are based on their profile, search/browsing history, what other people with similar traits/demographics are watching, and how likely are you to watch those movies. This is achieved through predictive modeling and heuristics with the data available.

# Types of Recommendation System :

### 1 ) Content Based :

- Content-based systems, which use characteristic information and takes item attriubutes into consideration .

- Twitter , Youtube .

- Which music you are listening , what singer are you watching . Form embeddings for the features .
	
- User specific actions or similar items reccomendation .
	
- It will create a vector of it .
	
- These systems make recommendations using a user's item and profile features. They hypothesize that if a user was interested in an item in the past, they will once again be interested in it in the future
	
- One issue that arises is making obvious recommendations because of excessive specialization (user A is only interested in categories B, C, and D, and the system is not able to recommend items outside those categories, even though they could be interesting to them).

### 2 ) Collaborative Based :
		
- Collaborative filtering systems, which are based on user-item interactions.
	
- Clusters of users with same ratings , similar users .
	
- Book recommendation , so use cluster mechanism .
	
- We take only one parameter , ratings or comments .
	
- In short, collaborative filtering systems are based on the assumption that if a user likes item A and another user likes the same item A as well as another item, item B, the first user could also be interested in the second item . 
	
- Issues are :

	- User-Item nXn matrix , so computationally expensive .

	- Only famous items will get reccomended .

	- New items might not get reccomended at all .   

### 3 ) Hybrid Based :
	
- Hybrid systems, which combine both types of information with the aim of avoiding problems that are generated when working with just one kind.

- Combination of both and used now a days .

- Uses : word2vec , embedding .           

# About this project:

This is a streamlit web application that can recommend various kinds of similar movies based on an user interest.
here is a demo,

* [Click here to run it live on server](https://movie-recommeder-system.herokuapp.com/)

# How to Run the Project:

## Prerequisites:
- Python 3.7 or higher
- pip (Python package installer)

## Step-by-Step Instructions:

### Step 1: Clone or Download the Repository
```bash
# If using git
git clone <repository-url>

# Or download and extract the ZIP file
```

### Step 2: Navigate to the Project Directory
```bash
cd Movie-Recommender-System-Using-Machine-Learning-master
```

### Step 3: Install Required Dependencies
```bash
pip install -r requirements.txt
```

**Note:** The requirements include:
- streamlit
- pandas
- requests
- scikit-learn (for generating similarity matrix if needed)

### Step 4: Generate Similarity Matrix (If Not Already Present)
If the `artifacts/similarity.pkl` file doesn't exist, you need to generate it:

```bash
python generate_similarity.py
```

This script will:
- Load the movie data from `artifacts/movie_dict.pkl`
- Create feature vectors from movie tags
- Compute cosine similarity matrix
- Save it as `artifacts/similarity.pkl`

### Step 5: Run the Streamlit Application
```bash
streamlit run app.py
```

The application will start and automatically open in your default web browser at:
- **Local URL:** http://localhost:8501

If it doesn't open automatically, you can manually navigate to the URL shown in the terminal.

### Step 6: Use the Application
1. Select a movie from the dropdown menu
2. Click the "Show Recommendation" button
3. View 5 similar movies with their posters, release years, and ratings

## Troubleshooting:

### Issue: "FileNotFoundError: artifacts/similarity.pkl"
**Solution:** Run `python generate_similarity.py` to generate the similarity matrix.

### Issue: "ModuleNotFoundError"
**Solution:** Make sure all dependencies are installed: `pip install -r requirements.txt`

### Issue: "streamlit: command not found"
**Solution:** Install streamlit: `pip install streamlit`

### Issue: App doesn't start
**Solution:** 
- Make sure you're in the correct directory (where `app.py` is located)
- Check that port 8501 is not already in use
- Try using the full path: `streamlit run "C:\full\path\to\app.py"`

## Alternative: Using Conda Environment (Optional)

If you prefer using conda:

```bash
# Create conda environment
conda create -n movie python=3.7.10 -y

# Activate environment
conda activate movie

# Install requirements
pip install -r requirements.txt

# Run the application
streamlit run app.py
```

# Demo:

<img src="Movie-Recommender-System-Using-Machine-Learning-master\demo\demo1.png" alt="workflow" width="70%">


# Dataset has been used:

* [Dataset link](https://www.kaggle.com/tmdb/tmdb-movie-metadata?select=tmdb_5000_movies.csv)

# Concept used to build the model.pkl file : cosine_similarity

1 . Cosine Similarity is a metric that allows you to measure the similarity of the documents.

2 . In order to demonstrate cosine similarity function we need vectors. Here vectors are numpy array.

3 . Finally, Once we have vectors, We can call cosine_similarity() by passing both vectors. It will calculate the cosine similarity between these two.

4 . It will be a value between [0,1]. If it is 0 then both vectors are complete different. But in the place of that if it is 1, It will be completely similar.

5 . For more details , check URL : https://www.learndatasci.com/glossary/cosine-similarity/
