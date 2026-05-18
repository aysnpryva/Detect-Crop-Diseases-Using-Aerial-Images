# Hava Şəkilləri ilə Bitki Xəstəliklərinin Aşkarlanması

Azərbaycanda dəqiq əkinçiliyi dəstəkləmək məqsədilə kассava bitkisinin
xəstəliklərini hava şəkillərindən klassifikasiya edən dərin öyrənmə modeli.

## Ümumi Baxış
EfficientNet-B3 modeli Cassava Leaf Disease dataseti üzərində train edilib —
5 kateqoriya: 4 xəstəlik və sağlam bitki.

## Nəticələr
| Metrik | Dəyər |
|--------|-------|
| Validation Dəqiqliyi | 86.15% |
| Makro F1 | 0.76 |
| Ən Yaxşı Epoch | 7/10 |

## Siniflər
| Label | Xəstəlik |
|-------|---------|
| 0 | Cassava Bakterial Yanığı (CBB) |
| 1 | Cassava Qəhvəyi Zolaq Xəstəliyi (CBSD) |
| 2 | Cassava Yaşıl Mozaika (CGM) |
| 3 | Cassava Mozaika Xəstəliyi (CMD) |
| 4 | Sağlam |

## Texnologiyalar
- Python 3.12
- PyTorch
- EfficientNet-B3 (transfer learning)
- Albumentations
- Scikit-learn

## Dataset
[Cassava Bitkisi Xəstəlik Dataseti](https://www.kaggle.com/datasets/killa92/crop-disease-image-classification-dataset/data)

## Model Arxitekturası
- Əsas model: EfficientNet-B3 (ImageNet-də öyrədilmiş)
- Giriş ölçüsü: 300x300
- Çıxış: 5 sinif
- Loss: Class weights ilə CrossEntropyLoss
- Optimizer: Adam (lr=1e-4)

## Augmentasiya
- Üfüqi və şaquli çevirмə
- Təsadüfi fırlatma
- Təsadüfi parlaqlıq/kontrast dəyişməsi
- Normallaşdırma (ImageNet ortalama/std)
