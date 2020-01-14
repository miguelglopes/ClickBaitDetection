# Group 2 - Detecting clickbait in Tweets

*Authors: Alexandre Gondar, Ana Ribeiro, Helena Magro, Miguel Lopes*

The following should be the folder structure of the project:

    App root 
        └──	model.ipynb
        └──  preprocessing.ipynb
        └──  visualization.ipynb
        │	
        └──  data
        │	   └── instances.jsonl
        │	   └── truth.jsonl
        |      └── media
        │	         └── (image files)
        │
        └──  binaries
        │	   └── GoogleNews-vectors-negative300.bin
        │      └── (other relevant binaries: .pkl or .h5)
        |
        └──  libraries
            └── attention.py



Our source-code consists, essentially, of 3 files:
* preprocessing.ipynb
* model.ipynb
* visualization.ipynb

The preprocessing should be run first. It will output the needed pickles to the binaries folder. These pickles will imported for the model input and the visualization input.

After running the preprocessing, one can run either the model or the visualization notebook.

The visualization notebook contains charts that we considered relevant to explore when designing the model architecture.

The model contains all the needed code to create, train, evaluate and optimize our clickbait prediction model.

Regarding the local libraries, we had to create a custom Keras attention layer, inspired on the [work of Yang et al.](https://www.cs.cmu.edu/~diyiy/docs/naacl16.pdf). For that, we created a class AttentionLayer that inherits from keras.layers.Layer. This was needed since keras doesn't have a built in attention layer. This local module is imported in the model notebook.

To get original data we used in this work, use [this link](http://www.uni-weimar.de/medien/webis/corpora/corpus-webis-clickbait-17/clickbait17-train-170630.zip) (big dataset) or [this link](http://www.uni-weimar.de/medien/webis/corpora/corpus-webis-clickbait-17/clickbait17-train-170331.zip) (small dataset).
To download the GoogleNews pre-trained model use [this link](https://s3.amazonaws.com/dl4j-distribution/GoogleNews-vectors-negative300.bin.gz).