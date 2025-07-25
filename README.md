
# API دیوان حافظ

دسترسی برنامه‌نویسی به غزلیات حافظ شیرازی

---

## معرفی API

این سرویس یک رابط برنامه‌نویسی (API) برای دسترسی به غزلیات حافظ ارائه می‌دهد. با استفاده از این API می‌توانید به راحتی در برنامه‌ها و پروژه‌های خود از غزلیات حافظ استفاده کنید.

---

## ویژگی‌های کلیدی

- دریافت غزل تصادفی  
- جستجوی پیشرفته در غزلیات  
- صفحه‌بندی غزلیات  
- پشتیبانی کامل از CORS برای دسترسی آسان از مرورگر  

---

## اطلاعات فنی

- فرمت پاسخ: JSON  
- کدگذاری: UTF-8  
- متدهای درخواست: GET  
- نرخ محدودیت (Rate Limit): بدون محدودیت  

---

## نقاط دسترسی (Endpoints)

### 1. دریافت غزل تصادفی

```
GET https://hafezapi.ir/ghazals/random
```

#### نمونه پاسخ:

```json
{
  "id": 442,
  "title": "غزل شمارهٔ ۴۴۲",
  "verses": [
    "به جان او که گرم دسترس به جان بودی",
    "کمینه پیشکش بندگانش آن بودی",
    "... (ادامه اشعار) ..."
  ],
  "meaning": "جانتان را برای رسیدن به مقصود در طبق اخلاص گذاشته‌اید..."
}
```

---

### 2. لیست غزلیات با صفحه‌بندی

```
GET https://hafezapi.ir/ghazals?page=1&per_page=10
```

#### نمونه پاسخ:

```json
{
  "page": 1,
  "per_page": 10,
  "total": 495,
  "data": [
    {
      "id": 1,
      "title": "غزل شمارهٔ ۱",
      "verses": ["الا یا ایها الساقی ادر کأساً و ناولها", "..."],
      "meaning": "مشکلاتتان بزودی حل خواهد شد..."
    },
    ...
  ]
}
```

---

### 3. جستجو در غزلیات

```
GET https://hafezapi.ir/search?q=عشق
```

#### نمونه پاسخ:

```json
{
  "query": "عشق",
  "results_count": 178,
  "results": [
    {
      "id": 1,
      "title": "غزل شمارهٔ ۱",
      "matches": [
        {
          "verse": "که عشق آسان نمود اوّل ولی افتاد مشکل‌ها",
          "index": 2
        }
      ]
    },
    ...
  ]
}
```

---

### 4. دریافت غزل با شناسه

```
GET https://hafezapi.ir/ghazals/1
```

#### نمونه پاسخ:

```json
{
  "id": 1,
  "title": "غزل شمارهٔ ۱",
  "verses": [
    "اَلا یا اَیُّهَا السّاقی اَدِرْ کَأسَاً و ناوِلْها",
    "که عشق آسان نمود اوّل ولی افتاد مشکل‌ها",
    "... (ادامه اشعار) ..."
  ],
  "meaning": "مشکلاتتان بزودی حل خواهد شد و شما به نیت خودتان خواهید رسید..."
}
```

---

## پشتیبانی و ارتباط

در صورت هرگونه سوال یا پیشنهاد می‌توانید از طریق Issues در همین مخزن اقدام کنید.


---

**موفق باشید!**
