<!-- Last Updated 3/17/2020, Mohamed Elbanan -->

# Visualization Module <small> radtorch.visutils </small>

!!! bug " Documentation Outdated. Please check again later for update."



Different tools and utilities for data visualization. Based upon Matplotlib and Bokeh.

    from radtorch import visutils





##show_dataloader_sample
    visutils.show_dataloader_sample(dataloader, num_of_images_per_row=10,
                            figsize=(10,10), show_labels=False)

!!! quote ""
    Displays sample of a dataloader with corresponding class idx

    **Arguments**

    - dataloader: _(dataloader object)_ selected pytorch dataloader.

    - num_of_images_per_row: _(int)_ number of images per row. (default=10)

    - figsize: _(tuple)_ size of displayed figure. (default = (10,10))

    - show_labels: _(boolen)_ display class idx of the sample displayed .(default=False)






##show_dataset_info
    visutils.show_dataset_info(dataset)

!!! quote ""
    Displays a Pandas DataFrame summary of the pytorch dataset information.

    **Arguments**

    - dataset: _(pytorch dataset object)_ target dataset to inspect.



## plot_pipline_dataset_info
    visutils.plot_pipline_dataset_info(dataframe, test_percent)

!!! quote ""
    Displays a graphical representation of the dataset information dataframe generated by visutils.show_dataset_info

    **Arguments**

    - dataframe: _(Pandas DataFrame)_ dataframe containing dataset information

    - test_percent: _(float)_ the percent of testing subset.




##show_metrics
    visutils.show_metrics(metric_source, metric='all',
                          show_points = False, fig_size = (600,400))

!!! quote ""
    Displays metrics created by model training loop.

    **Arguments**

    - metric_source: _(list)_ the metrics generated during the training process as by modelsutils.train_model()

    - metric: _(str)_ the metric to display. Options include 'all', 'accuracy' or 'loss'. (default='all')

    - show_points: _(boolean)_ display single points on graph (default = False)

    - fig_size: _(tuple)_ size of the displayed figure. (default=400,600)




##show_dicom_sample
    visutils.how_dicom_sample(dataloader, figsize=(30,10))

!!! quote ""
    Displays a sample image from a DICOM dataloader. Returns a single image in case of one window and 3 images in case of multiple window.

    **Arguments**

    - dataloader: _(dataloader object)_ selected pytorch dataloader.

    - figsize: _(tuple)_ size of the displayed figure. (default=30,10)






##show_roc
    visutils.show_roc(true_labels, predictions,
                      figure_size=(550,400), title='ROC Curve')

!!! quote ""
    Displays ROC curve and AUC using true and predicted label lists.

    **Arguments**

    - true_labels: _(list)_ list of true labels.

    - predictions: _(list)_ list of predicted labels.

    - figure_size: _(tuple)_ size of the displayed figure. (default=550,400)

    - title: _(str)_ title displayed on top of the output figure. (default='ROC Curve')




##show_nn_roc
    visutils.show_nn_roc(model, target_data_set,  device, figure_size=(600,400))

!!! quote ""
    Displays the ROC and AUC of a certain trained model on a target(for example test) dataset.

    **Arguments**

    - model: _(pytorch model object)_ target model.

    - target_data_set: _(pytorch dataset object)_ target dataset.

    - device: _(str)_ 'cpu' or 'cuda'.

    - figure_size: _(tuple)_ size of the displayed figure. (default=(600,400))




##show_confusion_matrix
    visutils.show_confusion_matrix(cm,target_names, title='Confusion Matrix',
                                  cmap=None,normalize=False,figure_size=(8,6))

!!! quote ""
    Given a sklearn confusion matrix (cm), make a nice plot. Code adapted from : https://www.kaggle.com/grfiv4/plot-a-confusion-matrix.

    **Arguments**

    - cm: _(numpy array)_ confusion matrix from sklearn.metrics.confusion_matrix.

    - target_names: _(list)_ list of class names.

    - title: _(str)_ title displayed on top of the output figure. (default='Confusion Matrix')

    - cmap: _(str)_ The gradient of the values displayed from matplotlib.pyplot.cm . See http://matplotlib.org/examples/color/colormaps_reference.html. (default=None which is plt.get_cmap('jet') or plt.cm.Blues)

    - normalize: _(boolean)_  If False, plot the raw numbers. If True, plot the proportions. (default=False)

    - figure_size: _(tuple)_ size of the displayed figure. (default=8,6)




##show_nn_confusion_matrix
    visutils.show_nn_confusion_matrix(model, target_data_set,
              target_classes, figure_size=(8,6), cmap=None)

!!! quote ""
    Displays Confusion Matrix for Image Classifier Model.

    **Arguments**

    - model: _(pytorch model object)_ target model.

    - target_data_set: _(pytorch dataset object)_ target dataset.

    - target_classes: _(list)_ list of class names.

    - figure_size: _(tuple)_ size of the displayed figure. (default=8,6)

    - cmap: _(str)_ the colormap of the generated figure (default=None, which is Blues)





## misclassified
    visutils.misclassified(true_labels_list, predicted_labels_list, img_path_list)

!!! quote ""
    Returns Dictionary of image path, true label and predicted label for instances not correctly classified by image classification model.

    **Arguments**

    - true_labels_list: _(list)_ list of true label idx

    - predicted_labels_list: _(list)_ list of predicted label idx

    - img_path_list: _(list)_ list of image paths

    **Output**

    - Dictionary of image path, true label and predicted label for instances not correctly classified by image classification model.




## show_misclassified
    visutils.show_misclassified(misclassified_dictionary, is_dicom = True,
                                num_of_images = 16, figure_size = (5,5))

!!! quote ""
    Displays sample images from misclassified instances.

    **Arguments**

    - misclassified_dictionary: _(dictionary)_ dictionary of image path, true labels and predicted labels generated by [visutils.misclassified](#misclassified)

    - is_dicom: _(boolean)_ True for DICOM images.

    - num_of_images: _(int)_ number of imgaes to display (default=16)

    - figure_size: _(tuple)_ size of displayed figure (default = (5,5))




## show_nn_misclassified
    visutils.show_nn_misclassified(model, target_data_set, num_of_images,
                          device, is_dicom = True, figure_size=(5,5))

!!! quote ""                          
    Displays sample of misclassified images of an image classification pipeline.

    **Arguments**

    - model: _(pytorch model object)_ target model.

    - target_data_set: _(pytorch dataset object)_ target dataset.

    - num_of_images: _(int)_ number of images to display.

    - device: _(str)_ 'cpu' or 'cuda'.

    - is_dicom: _(boolean)_ True for DICOM images. (default=True)

    - figure_size: _(tuple)_ size of displayed figure (default = (5,5))



## plot_features
    visutils.plot_features(feature_table, feature_names, num_features,
                            num_images, image_path_col, image_label_col)

!!! quote ""
    Displays a graphical representation of extracted imaging features from a Feature Extraction Pipeline. Features can be displayed overall or per class.


    **Arguments**

    - feature_table: _(Pandas DataFrame)_ feature table produced by feature extraction pipeline.

    - feature_names: _(list)_ list of imaging features produced by feature extraction pipeline.

    - num_features: _(int)_ number of imaging features produced by feature extraction pipeline.

    - num_images: _(int)_ number of images to show features for.

    - image_path_col: _(str)_ the name of the column which contains image path in the feature table.

    - image_label_col: _(str)_ the name of the column which contains image label idx in the feature table.
