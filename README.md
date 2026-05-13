Spotify Playlist Clustering

Machine learning prototype for automatic Spotify playlist generation using unsupervised learning.

The project evaluates whether clustering algorithms can create cohesive playlists based on Spotify audio features and whether ML can scale playlist curation better than manual expert selection.

Project Goal

I built a prototype that groups songs into playlists using Spotify audio features and K-Means clustering.

The project focuses on:

scalable playlist generation,
similarity detection between songs,
cluster quality evaluation,
business usability of generated playlists.
Dataset

The dataset contains Spotify tracks and audio features such as:

danceability
energy
valence
tempo
acousticness
instrumentalness
speechiness
liveness

Metadata columns and non-informative identifiers were removed before clustering.

Workflow
1. Data Cleaning

I removed:

duplicates,
missing values,
unnecessary metadata columns.
2. Feature Scaling

I compared multiple scaling methods:

StandardScaler
MinMaxScaler
RobustScaler
PowerTransformer
QuantileTransformer

StandardScaler produced the most stable clustering results.

3. Cluster Selection

I evaluated cluster quality using:

Silhouette Score
Calinski-Harabasz Index
Davies-Bouldin Index

The notebook includes:

metric-based optimal cluster selection,
business-focused clustering with k = 50.
4. Playlist Generation

I generated playlists using K-Means clustering.

The final business prototype uses:

BUSINESS_K = 50

to create a richer playlist catalog for evaluation.

5. Cluster Inspection

The notebook:

visualizes cluster distributions,
inspects small niche playlists,
lists tracks from selected clusters,
evaluates playlist cohesion manually.
Example Questions Answered
Can Spotify audio features detect similar songs?
Is K-Means suitable for playlist generation?
How many playlists should the system create?
Are generated playlists cohesive?
What additional data could improve recommendations?
Results

The prototype successfully grouped tracks with:

similar mood,
similar energy,
similar acoustic profiles.

However, Spotify audio features alone do not fully capture:

lyrical meaning,
cultural similarity,
trends,
artist relationships.

Some clusters still mixed genres despite similar audio characteristics.

Tech Stack
Python
Pandas
NumPy
Scikit-learn
Matplotlib
Seaborn
Jupyter Notebook
Repository Structure
.
├── spotify_playlist_clustering_github_clean_k50.ipynb
├── spotify_playlist_clusters_k50.csv
├── presentation/
│   └── spotify_playlist_clustering_presentation.pptx
└── README.md
Exporting Results

The notebook exports clustered tracks as:

spotify_playlist_clusters_k50.csv

Example export:

songs_clusters_df.to_csv(
    "spotify_playlist_clusters_k50.csv",
    index=False
)
Limitations
K-Means requires a fixed number of clusters.
Results are sensitive to feature scaling.
Audio features do not fully represent human music perception.
Genre overlap can reduce cluster clarity.
Future Improvements

Possible next steps:

hierarchical clustering,
DBSCAN,
user listening behavior,
skip rates and engagement metrics,
collaborative filtering,
embedding-based similarity models,
deep learning recommendation systems.
Presentation

The repository also includes a short business presentation prepared for a non-technical startup audience.

Topics covered:

prototype creation,
playlist evaluation,
feature selection,
cluster analysis,
business recommendations,
future roadmap.
Author

Tomasz Szymusiak
