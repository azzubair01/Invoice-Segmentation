# Invoice-Segmentation
- Recently I have been working on invoice data to extract the data and save it as structured data which will reduce the manual data entry process. Now it has been one of the big research among the community. In this blog, I prepared some samples of data so that we can work on performing custom object detection using tensorflow.

## Steps of Invoice-Segmentation
  1. Pre-process the images so that they are of the same size. In my case, I have 600 x 600 images.
  2. Split the images into train & test folders.
  3. Label the images using labelimg to generate xml file of the images.
  4. Convert the xml files to csv files using xml_to_csv script.
  5. Generate TFRecords of the csv files using generate_tf_records script.
  6. Select suitable models for object detection.
  7. Configure the pipeline and paths.
  8. Train & validate the model.
  9. View results on the tensorboard.
  10. Export the model.
  11. Test the model using the trained model.
  12. Generate csv file containing box coordinates.

<div style="text-align:center"><img src="./reference/processflow.png" /></div>
  
## Model Accuracy
- faster_rcnn_resnet101_v1_640x640_coco17_tpu-8 = 88.1 %
- faster_rcnn_resnet50_v1_640x640_coco17_tpu-8  = 87.8 %
- faster_rcnn_resnet152_v1_640x640_coco17_tpu-8 = 87.5 %
- efficientdet_d0_coco17_tpu-32                 = 76.7 %
- ssd_resnet50_v1_fpn_640x640_coco17_tpu-8      = 66.4 %
- ssd_mobilenet_v2_320x320_coco17               = 28.1 %

## Platform used
- Google Colaboratory for training & testing
- Local machine for testing

## Reference
- https://github.com/tzutalin/labelImg
- https://blog.tensorflow.org/2021/01/custom-object-detection-in-browser.html
- https://github.com/vigneshgig/Faster_RCNN_for_Open_Images_Dataset_Keras
