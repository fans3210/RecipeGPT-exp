## Overview
This is the github repo for 

```Helena H. Lee, Ke Shu, Palakorn Achananuparp, Philips Kokoh Prasetyo, Yue Liu, Ee-Peng Lim, and Lav R. Varshney. 2020. RecipeGPT: Generative Pre-training Based Cooking Recipe Generation and Evaluation System. In Companion Proceedings of the Web Conference 2020 (WWW 20 Companion), April 20-24, 2020, Taipei, Taiwan. ACM, New York, NY, USA, 4 pages. https://doi.org/10.1145/3366424.3383536 ```

This paper can be downloaded at [arxiv](https://arxiv.org/pdf/1909.07881.pdf)

We also provide an online website that allows the users to generate cooking recipes at [https://recipegpt.org/](https://recipegpt.org/)

Please contact ```helenalee.bt01@gmail.com``` if you have any questions or problems.

## Poster 
Our poster presented in WWW'20 could be found at [here](https://drive.google.com/file/d/1DD5BJRRQZ4qATP_w0TjOfXYKN4EYs2zY/view?usp=sharing)

## Project Structure
By default, the project assumes the following directory structure:

 
    +-- data                                    # Files that are within GitHub's file size limit
    ¦   +-- vocab.bin                           # A word embedding model, will be used in utils.tree
    ¦
    +-- big_data                                # Files that exceeds GitHub's file size limit
    ¦   +-- Download.md                         # Download link
    ¦ 
    +-- analysis                                
    ¦   +-- notebook 1-0, 1-1, 2, 3             # Useful for data pre-processing
    ¦   +-- notebook 4, 5                       # Useful for analyzing the generated texts
    ¦   +-- notebook 9                          # Compare the generated texts with human-written texts
    ¦ 
    +-- training                                
    ¦   +-- gpt-2                               # The source code modified from OpenAI GPT-2
    ¦       +--src/load_dataset_pad.py              # Padding and fields shuffing
    ¦       +--src/conditional_gen_web.py           # Input .txt files and receive the output in .txt files
    ¦       +--train_ppl_pickle.py                  # The main script for fine-tuning with recipe data
    ¦       +--train_ppl_scratch.py                 # The main script for training from scratch with recipe data
    ¦       ...
    ¦       
    ¦   +-- notebook 6                          # Commands of fine-tuning/training the model
    ¦   +-- notebook 7                          # Ask the model the generated the title/ingredients/instructions 
    ¦   +-- notebook 8                          # Evaluate the model perplexity
    ¦ 
    +-- common                                  # Import numpy, pickle, ... etc common packages
    +-- utils                                   # Some modules related to model evaluation

## Dataset
* We download and utilize the textual content of [Recipe1M](http://pic2recipe.csail.mit.edu/) That file is called ```layer1.json```
* We utilize the ```food_taxonomy.txt``` from [Here](https://www.researchgate.net/publication/288838055_Simple_food_taxonomy_compiled_from_Wikipedia_pages) to create an ingredient database .


## Environment
```
conda create -n recipegpt python=3.5 anaconda
pip install tensorflow-gpu==1.12.0 or pip install tensorflow==1.12.0
pip install -r requirements.txt
```
## 
