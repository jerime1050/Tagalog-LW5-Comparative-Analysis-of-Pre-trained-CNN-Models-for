# Tagalog-LW5-Comparative-Analysis-of-Pre-trained-CNN-Models-for


# Google Colab link: https://colab.research.google.com/drive/1hRVcSQb2tU2fFmlNb4Mz4XLoiyfulRTW?usp=drive_link

A. Model Performance

Which pre-trained model achieved the highest accuracy? Why?
EfficientNetB0 obtained the highest accuracy among the tested models. This is because it applies compound scaling, which efficiently balances the network’s depth, width, and input resolution. As a result, the model can extract more meaningful features while maintaining computational efficiency.

Which model showed the lowest performance? What may have caused this?
NASNetMobile recorded the lowest performance. Since it is mainly designed for lightweight mobile applications, its smaller architecture may not be powerful enough to capture complex patterns in datasets containing 20 different classes. This limitation can lead to underfitting, especially when classes have subtle visual similarities.

How did the loss values differ among the models?
EfficientNetB0 achieved the lowest validation loss, indicating stronger generalization capability. MobileNetV2 produced moderate loss values, offering a balance between speed and accuracy. Meanwhile, NASNetMobile generated the highest loss values, suggesting weaker feature learning and possible underfitting.

B. Evaluation Metrics

Why is accuracy alone insufficient in evaluating a model?
Accuracy alone may not fully represent model performance, especially when dealing with imbalanced datasets. A model may achieve high accuracy simply by predicting the majority class while failing to classify minority classes correctly. Therefore, additional metrics such as precision, recall, and F1-score are necessary for a more reliable evaluation.

Which model achieved the best F1-score? What does this imply?
EfficientNetB0 achieved the highest F1-score. This indicates that the model maintained a strong balance between precision and recall, minimizing both false positive and false negative predictions.

How did precision and recall vary among the models?
EfficientNetB0 demonstrated high precision and recall, resulting in more dependable predictions. MobileNetV2 showed slightly lower recall, meaning it produced more false negatives. NASNetMobile, on the other hand, had lower precision, which suggests a higher occurrence of false positives.

C. Confusion Matrix Analysis

Which classes were commonly misclassified?
Classes with closely related visual characteristics, such as similar animal breeds, vehicle types, or fruits with comparable colors and textures, were more likely to be incorrectly classified.

What trends were observed in the confusion matrix?
Most prediction errors occurred between visually similar classes. EfficientNetB0 displayed stronger diagonal dominance, which indicates a higher number of correct classifications. In contrast, NASNetMobile produced more off-diagonal values, reflecting a greater number of misclassifications.

D. ROC and AUC

Which model achieved the highest AUC score?
EfficientNetB0 produced the highest AUC score, with values closest to 1.0.

What does the AUC score indicate about model performance?
AUC evaluates the model’s ability to distinguish between different classes. A higher AUC score means the model is more effective in ranking positive classes above negative ones, even if the probability estimates are not perfectly calibrated.

E. Explainability (Grad-CAM)

What insights did Grad-CAM provide regarding model decisions?
Grad-CAM demonstrated that the models mainly focused on meaningful foreground features, such as animal faces or vehicle components, rather than irrelevant background details.

Did the models focus on appropriate image regions?
Yes. EfficientNetB0 and MobileNetV2 consistently highlighted relevant and discriminative image areas. However, NASNetMobile occasionally focused on smaller or less informative regions.

Which model generated the most effective heatmaps?
EfficientNetB0 produced the most accurate and class-specific heatmaps, clearly emphasizing the image regions associated with the predicted category.

F. Model Comparison and Improvement

Which model is most suitable for deployment? Why?
MobileNetV2 is more appropriate for deployment on mobile and edge devices because it offers a good balance between computational efficiency and accuracy. On the other hand, EfficientNetB0 is better suited for cloud or high-performance server environments where achieving maximum accuracy is more important.

How can the best-performing model be improved further?
The performance of the model can be enhanced by fine-tuning the upper layers after initial training, applying more data augmentation techniques such as rotation, zooming, flipping, and brightness adjustments, increasing the number of training epochs with early stopping, and using label smoothing to reduce prediction overconfidence.

G. Real-World Application

How can this model be applied in real-world situations?
One practical application is a 20-class waste classification system capable of identifying materials such as plastic, paper, glass, and metal. This system can be integrated into recycling facilities or smart waste bins to automate waste segregation.

What are the possible risks of deploying an inaccurate model?
Incorrect classifications may contaminate recycling processes and reduce operational efficiency. In critical fields such as healthcare or safety systems, inaccurate predictions may lead to harmful outcomes and reduced user confidence.

How can the system be integrated into a mobile or web application?
The trained model can be converted into TensorFlow Lite for mobile deployment or TensorFlow.js for web applications. A backend service using Flask or FastAPI can serve the model through a REST API. The workflow typically involves capturing an image, preprocessing it, sending it to the API for prediction, and displaying the classification result to the user.
