# questionCaptionMatchModels

Code for identifying True vs False Premise questions for a given image as described in the paper, Question Relevance in VQA:
Identifying Non-Visual And False-Premise Questions,  https://arxiv.org/pdf/1606.06622v2.pdf

##Prerequisites:

- After cloning the repository, go inside folder.

- ```mkdir w2vmodel```

- Download the Google Word2Vec Dictionary from here: https://drive.google.com/file/d/0B7XkCwpI5KDYNlNUTTlSS21pQmM/edit .

- Extract the compressed file and place the dictionary file inside ```w2vmodel/``` folder. 

##How to run the code:

```python questionCaptionModel.py --captype [option1] --model [option2] --loadweights [option3] --saveModel [option4]```

Options are:

- [option1] :
  - ```qc``` for question-caption similarity.
  - ```qq``` for question-question similarity.
  - ```qdq``` This method is not described in the paper and is an experimental method where the similarity is computed between the test question and a set of diverse questions generated by a captioning model. 
  
- [option2] :
  - ```bow``` : concatenates test question and generated question/caption features by Bag-of-Words technique 
  - ```avgw2v``` : concatenates test question and generated question/caption features by averaging word2vec.
  - ```lstm``` : concatenates test question and generated question/caption features by feeding in the word2vec vectors into an lstm
  
- [option3] : (optional) Path of pretrained weights. You will find some pretrained weights in the ```pretrainedCaptionFiles/``` folder. Note that these are not the exact models used in the paper, and so, the numbers might differ slightly, but will be very close. 

- [option4] : If [option3] is not specified, the training is executed. Set ```FALSE``` to NOT save your trained model at the end of execution, default value is ```TRUE``` (i.e trained model will be saved)

Please contact ray93@vt.edu if you have any questions.
