# NYT_WordCount

This repository contains code to perform simple MapReduce Jobs like word count and word co-occurrence on New York Times articles data.

1) Data Collection:
- I collected New York Times articles using Article search API to lookup articles by keywords.

2) Setting up MapReduce Pipeline:

- The preprocessing of data is done inside Mapper itself.
- wordcount MapReduce job written in python which returns the frequency of the words appearing in the collected NYT articles.
- wordCooccurrence MapReduce job written in python to find the most cooccuring words in the same paragraph for each of the top 20 words     with highest frequency

- The data and MapReduce scripts are uploaded into AWS S3 Bucket. Using AWS EMR Service, the MapReduce Jobs are performed with input data, mapper.py, reducer.py and output folder passed as arguments in the Hadoop Streaming step.
 
- install_libraries.sh is given as a Bootstrap actions argument so that this shell script can install required packages (like nltk to perform pre-processing) onto EMR Cluster nodes.

3) Visualizing Output:

- The top most results of word counts and word-cooccurrences were visualized by creating a wordcloud using Tableau. These images are present in Images folder.
