Superstore Sales Analysis – End-to-End Data Project

تحليل بيانات مبيعات متجر "Superstore" من البداية حتى الداشبورد النهائي، كمثال تطبيقي لـ Data Analysis Pipeline باستخدام Python و Power BI.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

📁 الملفات المرفوعة:
- Superstore_Analysis.ipynb: دفتر Jupyter من Google Colab يحتوي على كود تنظيف البيانات والتحليل.
- Superstore_Cleaned.xlsx: ملف Excel نظيف بعد معالجة البيانات، جاهز للاستخدام في Power BI.
- Superstore_Analysis.pbix: داشبورد تفاعلي مكتمل في Power BI.
- Superstore_Dashboard.pdf: نسخة ثابتة (PDF) من الداشبورد للعرض السريع.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

🐍 أوامر بايثون المستخدمة (في Google Colab):

المكتبات:
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from google.colab import files

أبرز الخطوات:
1. تحميل البيانات:
   df = pd.read_csv('Superstore.csv', encoding='latin1')

2. تنظيف البيانات:
   - حذف الصف الفارغ: df = df.dropna(how='all')
   - تحويل التواريخ:
     df['Order Date'] = pd.to_datetime(df['Order Date'], format='%m/%d/%Y')
     df['Ship Date'] = pd.to_datetime(df['Ship Date'], format='%m/%d/%Y')

3. إنشاء أعمدة تحليلية جديدة:
   df['Order Year'] = df['Order Date'].dt.year
   df['Order Month'] = df['Order Date'].dt.month
   df['Shipping Duration'] = (df['Ship Date'] - df['Order Date']).dt.days
   df['Profit Margin (%)'] = (df['Profit'] / df['Sales']) * 100
   df['Return Flag'] = df['Profit'] < 0
   df['Order Month Name'] = df['Order Date'].dt.month_name()

4. إعادة ترتيب الأعمدة حسب المجموعات المنطقية.

5. تصدير الملف النهائي:
   df.to_excel('Superstore_Cleaned.xlsx', index=False)
   files.download('Superstore_Cleaned.xlsx')

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

🔍 أبرز التحليلات:

1. معلومات الطلب:
   - نمو المبيعات والربح من 2014 إلى 2017.
   - متوسط مدة الشحن حسب طريقة الشحن.
   - علاقة مدة الشحن بالربح.

2. معلومات العميل:
   - قطاع "Consumer" هو الأعلى ربحًا (ليس Corporate).
   - أعلى 3 ولايات ربحًا: California, New York, Washington.
   - خريطة جغرافية لتوزيع الربح.

3. معلومات المنتج:
   - فئة "التكنولوجيا" (Technology) هي الأكثر ربحية (هامش ربح ~38%).
   - فئة "الأثاث" (Furniture) تعاني من خسائر في 33.7% من طلباتها.
   - أعلى 10 منتجات ربحًا كلها من فئة التكنولوجيا.

4. المقاييس المالية:
   - الطلبات بكميات كبيرة (11+ وحدة) أكثر ربحية من الطلبات الفردية.
   - خصومات ≥ 30% تسبب خسائر فادحة — مثال: طلب واحد بخصم 70% → خسارة $6,599.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

📊 داشبورد Power BI يتضمن:
- مؤشرات أداء رئيسية (إجمالي المبيعات، الربح، هامش الربح).
- تحليل زمني (حسب السنة والربع).
- خريطة جغرافية للولايات.
- تحليل الخسائر حسب الفئة والخصم.
- جدول تنبيه للطلبات عالية الخصم والخاسرة.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

💡 التوصيات الاستراتيجية:
1. تجنب الخصومات >30% على منتجات الأثاث باهظة الثمن.
2. ركّز الحملات على فئة "التكنولوجيا".
3. شجّع على الطلبات بكميات كبيرة (لأنها أكثر ربحية).
4. راجع سياسات التسعير للعملاء المتكررين الذين يسببون خسائر.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

🛠️ الأدوات المستخدمة:
- Python (pandas, numpy) → لتنظيف البيانات
- Google Colab → للتنفيذ والتوثيق
- Power BI Desktop → لبناء الداشبورد
- GitHub → لعرض المشروع كسابقة أعمال

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

ملاحظة: ملف PDF مرفق كمرجع بصري سريع، لكن الملف الأساسي هو Superstore_Analysis.pbix لأنه يحتفظ بالتفاعلية.