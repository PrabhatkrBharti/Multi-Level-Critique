# Please be Polite to Your Peers: A Multi-Task Model for Assessing the Tone and Objectivity of Critiques of Peer Review Comments

## Download the project source folder

Can download the source code using `git clone` or the `zip file`.

## Dataset:
We proffer a 2-fold taxonomy for 5-level Constructiveness and 3-level Politeness Tone in a review and publically release a novel corpus of ~2700 annotated review sentences with an Inter-Annoatation Agreement of 0.882 (Krippendorff's alpha) for the scientific community. We introduce a novel annotation scheme  comprising 5 levels of Constructiveness : (1) Highly Non-Constructiveness, (2) Non-Constructiveness, (3) Neutral, (4) Constructiveness, and (5) Highly Constructiveness and 3-levels of Politeness Tone : (1) Impolite, (2) Neutral and (3) Poliite. The dataset is accrued from various multi-disciplinary venues like NIPS, ICLR, Publons, and ShitMyReviews. 

## Notebooks:

### 1) Data Pre-Processing :

This [notebook](https://github.com/meithnav/IIT-2Layers/blob/main/notebooks/preprocess-and-generate-embeddings.ipynb) consists all the code for EDA like data cleaning, resolving data imbalance by upsampling, ohe-hot-encoding the y-labels and finally storing the embeds.

### 2) Our Proposed Model and Baselines :

This [notebook](https://github.com/meithnav/IIT-2Layers/blob/main/notebooks/our-proposed-multitask-model-AND-baselines.ipynb) consists of our Proposed model (Toxic-Bert) and different variants of our competitve baselines analysis, wherein we feed <b> HateBERT/SciBERT/RoBERTa Embeddings</b> (either of them at a time). In the notebook `uncomment` the appropriate `name` and `embed_model_name`, the one that you want to reproduce and let the others be commented. 

### 3) Ablation Study :

This [notebook](https://github.com/meithnav/IIT-2Layers/blob/main/notebooks/ablations-model.ipynb) consists of the ablation variants of our proposed model to examine the efficacy of the layers in our model by experimenting with its ablation variants. We have considered the following models - WithoutBiLSTM WithoutAttention layer, WithoutBothBiLSTM-and-Attention layers, and WithoutBoth layers.

NOTE: Make sure you comment out the appropriate layers in the `DEFINE MODEL` section while running the notebook and update `is_BiLSTM flag` to true or false as appropriate.


### 4) Inter Annotator Agreement :
This [notebook](https://github.com/meithnav/IIT-2Layers/blob/main/IAA/iaa.ipynb) depicts Fleiss Kappa, Krippendroff Alpha, and Cohen Kappa scores, suggesting how well multiple annotators have annoatated the review following the proposed annotation guidelines. 


### 5) Heatmap Analysis :

This [notebook](https://github.com/meithnav/IIT-2Layers/blob/main/notebooks/heatmap.ipynb) loads our proposed model and produces a sentence-wise heatmap distribution for aspect categories for 2 selected Reviews which is discussed in depth in our paper.

#### IMPORTANT POINTS BEFORE RUNNING :

a) Change the `URL PATH` accordingly before loading the dataset(pickle files) <br>
b) The 1st tab in the notebook consists all the additional dependencies required and will be downloaded on running the cell <br>
c) For `SAVE_PATH` set the URL path where you want to save the trained model <br>

Once all the setup is complete then execute `run all`.

## Libraries & Dependencies used:

  <li>TensorFlow
  <li>Keras
  <li>Hugging Face
  <li>Matplotlib, numpy, pandas, pickle
  <li> krippendorff
