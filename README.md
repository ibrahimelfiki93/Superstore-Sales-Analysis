# Superstore Sales Analysis – End-to-End Data Project

تحليل بيانات مبيعات متجر "Superstore" من البداية حتى الداشبورد النهائي، كمثال تطبيقي لـ **Data Analysis Pipeline** باستخدام Python و Power BI.

---

## 📁 الملفات المرفوعة

| الملف | الوصف |
|------|--------|
| `Superstore_Analysis.ipynb` | دفتر Jupyter (من Google Colab) يحتوي على **كامل خطوات تنظيف البيانات، الإثراء، والتحليل الاستكشافي** باستخدام Python. |
| `Superstore_Cleaned.xlsx` | ملف Excel نظيف، جاهز للاستخدام في أي أداة تحليل (مثل Power BI أو Excel Pivot Tables). يحتوي على جميع الأعمدة الأصلية + أعمدة تحليلية جديدة. |
| `Superstore_Analysis.pbix` | داشبورد تفاعلي مكتمل في Power BI، يعرض رؤى الأعمال عبر مؤشرات أداء رئيسية، خرائط جغرافية، وتحليلات زمنية وفئوية. |
| `Superstore_Dashboard.pdf` | نسخة ثابتة (PDF) من الداشبورد لعرض سريع دون الحاجة لفتح Power BI. مثالية للمشاركة أو الإرفاق في تقارير. |

---

## 🐍 أوامر بايثون المستخدمة (في Google Colab)

تم استخدام لغة Python مع المكتبات التالية:

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from google.colab import files
