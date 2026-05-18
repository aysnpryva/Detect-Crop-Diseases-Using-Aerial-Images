# Hava Şəkilləri ilə İş Zamanı Qarşılaşılan Çətinliklər

## Dataset Çətinlikləri
- Metadata-da 21,397 sətr olsa da yalnız 17,938 şəkil mövcud idi —
  3,459 çatışmayan fayl train-dən əvvəl filterləndi.
- Ciddi sinif balanssızlığı: CMD-dən 13,158, CBB-dən isə yalnız 1,087
  şəkil vardı. Bu, modelin az təmsil olunan siniflərdə zəif işləməsinə
  səbəb oldu.

## Model Çətinlikləri
- EfficientNet-B3 ImageNet çəkiləri ilə transfer learning vasitəsilə
  train edildi — bu konvergensiyaya əhəmiyyətli dərəcədə kömək etdi.
- Epoch 7-dən sonra overfitting başladı — validation dəqiqliyi 86.15%-də
  zirvəyə çatdı, sonra azaldı, train dəqiqliyi isə artmağa davam etdi.
- GPU uyğunsuzluğu: Kaggle-ın P100 GPU-su quraşdırılmış PyTorch versiyası
  ilə uyğun deyildi. T4 x2 GPU-ya keçməklə həll edildi.

## Augmentasiya
- Üfüqi/şaquli çevirmə, təsadüfi fırlatma və parlaqlıq/kontrast dəyişməsi
  real sahə şəraitini simulyasiya etmək üçün train şəkillərinə tətbiq edildi.
- Augmentasiya modelin ümumiləşdirmə qabiliyyətini artırmaqda həlledici rol
  oynadı.

## Nəticələr
- Ən Yaxşı Validation Dəqiqliyi: 86.15%
- Makro F1: 0.76
- CMD — F1: 0.95, CBB — F1: 0.62 (ən az data)
