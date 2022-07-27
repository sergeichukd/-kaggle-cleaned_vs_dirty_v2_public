# kaggle-cleaned_vs_dirty_v2_public
## Colab notebook for kaggle competition [Cleaned vs Dirty V2](https://www.kaggle.com/competitions/platesv2/overview)
- [My kaggle profile](https://www.kaggle.com/sergeichukd)
- Max score: 0.92
- Train dataset size: 40
- See solution [here](https://github.com/sergeichukd/kaggle-cleaned_vs_dirty_v2_public/blob/main/cleaned_vs_dirty_v2_public.ipynb) or in [colab](https://colab.research.google.com/drive/1BlqgZRzgY6YKVaefHRYD7yjEYfuRuhgn?usp=sharing)

## Key features
- Use [Albumentations](https://github.com/albumentations-team/albumentations/) lib to boost transform speed
- Augmentations (ToGray, ColorJitter, HorizontalFlip, VerticalFlip, Perspective, Normalization)
- Two stage Background separating with Grab Cut algorithm
- Mix separated plates and backgrounds independently
- Take best accuracy model after training
- Transfer Learning: use resnet18 with pretrained layers up to layer4 (layer4 is not pretrained)
- Use Adam optimizer with ReduceLROnPlateau lr-scheduler and BCE-loss
- Ensemble (5 models) trained with Stratified k-fold scheme (to use all available 40 images, where in each fold 32 - train, 8 - validation)

## Debug
- Use accuracy and f1-score metrics
- Use Grad Cam
