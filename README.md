# English-to-Hindi-Translation

The project is about translating English sentences to Hindi sentences using Transformers.<br>
I have used Tensorflow for the project and [this](https://keras.io/examples/nlp/neural_machine_translation_with_transformer/) article has helped to understand its implementation.<br>

### Dataset
Dataset used can be found [here](https://www.kaggle.com/devkhant24/english-to-hindi-text-corpus).<br>
It contains around 100K pairs of English and Hindi sentences.<br>

### Processing Text
First I have done basic text processing which includes things like lowering of sentences, removing any URLs, removing digits etc.<br>
**[Start]** and **[End]** tags are then added to Hindi Sentences.<br>
TextVectorization from keras is used to create sentence vectors.<br>
The vocabulary size is 20000 and sentence length is 20.<br>

### Model


![Transformer](https://user-images.githubusercontent.com/57898986/146673698-bdc1231c-d27d-45d4-b27c-962fb499c3f1.png)
<br><br>

Here 80K samples are taken for training each with a length <= 20 words.<br>
Here in Transformer model I have used only 1 encoder and 1 decoder.<br>
The Embedding dim is 128, no. of heads in MultiHeadAttention is 10, latent dim is 2048 which is used in Feed Forward Network with dropout of 0.2.<br>

### Training and Evaluating Model
The Epochs are set to 50 with Optimizer as Adam, Loss as sparse_categorical_crossentropy and Metric as accuracy.<br>
Two callback functions Reduce LR on Plateau and Early Stopping are also used.<br><br>

After evaluating on 500 samples the BLEU score was 24.5.<br>
The BLEU score is not that great but still I **learned** a lot about Transformer.
