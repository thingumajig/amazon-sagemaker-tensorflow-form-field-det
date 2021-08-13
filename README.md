## TensorFlow 2 Object Detection API SageMaker for form field detection



### Instructions


Follow the step-by-step guide by executing the notebooks in the following folders:
* 1_prepare_data/prepare_data.ipynb - TODO
* 2_train_model/train_model.ipynb - TODO
* 3_predict/deploy_endpoint.ipynb
* 2_train_model/model-exporter.ipynb - to export existing model


### Monitor model training jobs with Tensorboard
SageMaker debugger allows you to [capture TensorBoard data](https://sagemaker.readthedocs.io/en/stable/amazon_sagemaker_debugger.html#capture-real-time-tensorboard-data-from-the-debugging-hook) into a chosen S3 location and monitor the training progress in real-time with TensorBoard.  
See 2_train_model/train_model.ipynb for command details.

You can start the TensorBoard server from your notebook with the following command:

```python
job_artifacts_path = estimator.latest_job_tensorboard_artifacts_path()
tensorboard_s3_output_path = f'{job_artifacts_path}/train'

!F_CPP_MIN_LOG_LEVEL=3 AWS_REGION=<ADD YOUR REGION HERE> tensorboard --logdir=$tensorboard_s3_output_path
```

TensorBoard server will run on your local notebook instance and you can open it by visiting the following url (the default port is typically 6006: 
```
https://your-notebook-instance-name.notebook.your-region.sagemaker.aws/proxy/6006/
```



