# Model Performans Hesabatı

## Validation Nəticələri
- **Dəqiqlik:** 86.15%
- **Makro F1:** 0.76
- **Ən Yaxşı Epoch:** 10-dan 7-ci

## Sinif üzrə Performans
| Sinif | Precision | Recall | F1 | Dəstək |
|-------|-----------|--------|----|--------|
| CBB | 0.60 | 0.64 | 0.62 | 184 |
| CBSD | 0.70 | 0.78 | 0.74 | 366 |
| CGM | 0.81 | 0.76 | 0.78 | 399 |
| CMD | 0.95 | 0.95 | 0.95 | 2206 |
| Sağlam | 0.71 | 0.69 | 0.70 | 433 |

## Əsas Müşahidələr
- CMD ən yüksək F1 (0.95) aldı — train datasında ən çox şəkil ona aiddir
- CBB ən aşağı F1 (0.62) aldı — ən az şəkilə sahib sinifdir
- Model CBB-ni 32 dəfə Sağlam kimi təyin etdi — real istifadədə təhlükəlidir
- CGM və CMD vizual oxşarlığı səbəbindən 50 dəfə qarışdırıldı

## Train Müşahidələri
- Overfitting epoch 7-dən sonra başladı
- Ən yaxşı model epoch 7-də saxlanıldı — val dəqiqliyi 86.15%
- Class weights az təmsil olunan siniflərin öyrənilməsinə kömək etdi

## Nəticə
Model 88% hədəfinə yaxın 86.15% validation dəqiqliyi əldə etdi.
Əsas problem sinif balanssızlığıdır — yalnız 1,087 şəkilli CBB,
13,158 şəkilli CMD-dən əhəmiyyətli dərəcədə zəif işlədi.
