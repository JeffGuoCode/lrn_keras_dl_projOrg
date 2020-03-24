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
  
## Important functions/class for prediction task
* prepare test data.
the data would be represented in json format, i.e., [{'image_id':xxx}, {'image_id':yyy}, ...]
 ```samples = image_dir_to_json(image_dir, img_type='jpg')```
* model build
```nima_tech = Nima(base_model_name, weights=None)
    nima_tech.build()
    nima_tech.nima_model.load_weights(weights_file_tech)
```
* train_data_generator and test_data_generator
* train and predict


    
