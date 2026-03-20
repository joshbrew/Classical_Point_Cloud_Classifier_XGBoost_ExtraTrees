## XGBoost and ExtraTrees Point Cloud Classification
Just a vibe-coded attempt to get really good point cloud classification results without deep learning methods. Our best model with pretty poor class sample variety has a geometric F1 score of 0.89 on 4 classes (trees, ground, cars, buildings). That's approaching competitive levels, but the test sampling quality was intentionally poor so this is not the maximum performance this model is really capable of.

The winning method uses KNN, context-splitting for imbalanced classes, and automatic hyperparameter tuning on a mix of manually and automatically selected features based on literature support. Sources should all be cited in the ipynb.

Corvallis, OR 4-class classification, best result:
<img width="3632" height="163" alt="image" src="https://github.com/user-attachments/assets/a615cc1d-beb4-4c52-bdf1-68fb66dfce28" />
<img width="2201" height="315" alt="test_KitchenSink_HierarchicalExtraTreesTunedContextKNN_side" src="https://github.com/user-attachments/assets/8b5b1cf0-a42d-4800-97ec-df01bbd8d3dd" />
<img width="1502" height="1292" alt="test_KitchenSink_HierarchicalExtraTreesTunedContextKNN_confusion_matrix" src="https://github.com/user-attachments/assets/f57d8e05-88ce-4af2-88ec-9216b5e4b075" />

Top view, you can see the top right corner and the flat buildings get garbled, but the cars in the parking lots nearby those are pretty consistent:
<img width="1390" height="1601" alt="full_HierarchicalExtraTreesTunedContextKNN_top_detailed" src="https://github.com/user-attachments/assets/6110eb9e-2982-4bc6-89ec-07e7b0cb02b9" />
Side view:
<img width="1601" height="112" alt="full_HierarchicalExtraTreesTunedContextKNN_side_detailed" src="https://github.com/user-attachments/assets/6f599902-b94f-4a61-8bd5-103b7da67e26" />

Pretty neat! The training data was very limited with a lack of variety so this is about as good as you could do without more samples. The model generalizes to any amount of classes and sample data, and is chunked up for laptop-scale ops. This is just a resources for whoever to reference.
