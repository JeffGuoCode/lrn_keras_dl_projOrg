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
* test_data_generator
```data_generator_tech = TestDataGenerator(samples, image_dir, 64, 10, nima_tech.preprocessing_function(),      img_format=img_format) ```
* predict
```predictions_tech = predict(nima_tech.nima_model, data_generator_tech)```
* save results
```
    if predictions_file is not None:
        save_json(samples, predictions_file)
```

## Important functions/class for training task
* tbc

## How to define the date_generator
re-define the __getitem_  and __len__function
refer to <https://stanford.edu/~shervine/blog/keras-how-to-generate-data-on-the-fly>

## How use docker

  
