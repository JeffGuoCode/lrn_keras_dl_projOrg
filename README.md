# Learning notes on keras deep learning project structure

This repo records my personal thoughts and reflections about how to organize a deep learning project with keras being used.
* The project file structure
* Important functions

The idea of doing this post originates from Google's AI project, image quality assessment, refer to <https://github.com/idealo/image-quality-assessment#datasets>. 

## Project main structure
* data_downloader (for data downloading, it's added later)
* entrypoints (shell scripts for prediction, training tasks by calling src/evaluator/predict.py or src/trainer/train.py)
* models (model files)
* src
  * evaludator
    * predict.py
  * trainer
    * train.py
  * handler
    * model_builder.py (build model)
    * date_generator.py (generate training and test dataset in batch)
  * test (test scripts)
  * utils
  * requirements.txt
  
## Important functions/class
* prepare data. prepare test if only got prediction task. prepare train and test if got training task as well by using train_test_split function.
* model build
* train_data_generator and test_data_generator
* train and predict


    
