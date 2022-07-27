# kaggle-cleaned_vs_dirty_v2_public
## Colab notebook for kaggle competition [Cleaned vs Dirty V2](https://www.kaggle.com/competitions/platesv2/overview)
- [My kaggle profile](https://www.kaggle.com/sergeichukd)
- [Max score: 0.92](https://www.kaggle.com/competitions/platesv2/submissions?group=selected&page=1&pageSize=100)
- Train dataset size: 40 images
- See solution [here](https://github.com/sergeichukd/kaggle-cleaned_vs_dirty_v2_public/blob/main/cleaned_vs_dirty_v2_public.ipynb) or in [colab](https://colab.research.google.com/drive/1BlqgZRzgY6YKVaefHRYD7yjEYfuRuhgn?usp=sharing)

## Key features
- [Albumentations](https://github.com/albumentations-team/albumentations/) lib to boost transform speed
- Augmentations (ToGray, ColorJitter, HorizontalFlip, VerticalFlip, Perspective, Normalization) for model robustness
- Two stage Background separating with Grab Cut algorithm and mix separated plates and backgrounds (to enlarge train dataset)
- Take the best accuracy model after training (to avoid model overfitting)
- Transfer Learning: use resnet18 with pretrained layers up to layer4 (to solve small dataset problem)
- Adam optimizer with ReduceLROnPlateau lr-scheduler and BCE-loss (for better convergency)
- Ensemble (5 models) is trained with Stratified k-fold scheme (to use all available 40 images, where 32 - train, 8 - validation in each fold)

## Model debug methods
- Accuracy and f1-score metrics
- GradCAM
