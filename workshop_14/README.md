# Практична робота №14
**Тема:** Оптимізація зображень за допомогою Squoosh

## Мета
Ознайомитися із методами стиснення зображень (lossless та lossy), дослідити вплив зміни розміру на якість та вагу файлу, а також навчитися адаптувати зображення для різних цільових застосувань (Web, Mobile, Retina).

## 1. Теоретичні відомості
**Squoosh** — це веб-інструмент для оптимізації зображень, який дозволяє порівнювати різні алгоритми стиснення в реальному часі.
* **Lossless (без втрат):** Зменшення розміру файлу без зміни пікселів (PNG, WebP Lossless).
* **Lossy (з втратами):** Зменшення розміру за рахунок відкидання частини інформації, яку людське око майже не помічає (MozJPEG, AVIF, WebP).

## 2. Аналіз вихідних файлів
Для роботи було обрано три типи зображень:

| Тип | Файл | Формат | Розмір | Опис |
| --- | --- | --- | --- | --- |
| **Фотографія** | `nature.jpg` | JPEG | 451 КБ | Фото природи, багато деталей і градієнтів. |
| **Скріншот** | `screenshot.png` | PNG | 145 КБ | Інтерфейс із текстом і пласкими кольорами. |
| **Графіка** | `ford.jpg` | JPEG | 11,5 КБ | Логотип, мінімальна кількість кольорів. |
| **Графіка** | `ford.jpg` | JPEG | 11,5 КБ | Логотип, мінімальна кількість кольорів. |
| **Графіка** | `ford.jpg` | JPEG | 11,5 КБ | Логотип, мінімальна кількість кольорів. |
| **Графіка** | `ford.jpg` | JPEG | 11,5 КБ | Логотип, мінімальна кількість кольорів. |
| **Графіка** | `ford.jpg` | JPEG | 11,5 КБ | Логотип, мінімальна кількість кольорів. |
| **Графіка** | `ford.jpg` | JPEG | 11,5 КБ | Логотип, мінімальна кількість кольорів. |
| **Графіка** | `ford.jpg` | JPEG | 11,5 КБ | Логотип, мінімальна кількість кольорів. |
| **Графіка** | `ford.jpg` | JPEG | 11,5 КБ | Логотип, мінімальна кількість кольорів. |
| **Графіка** | `ford.jpg` | JPEG | 11,5 КБ | Логотип, мінімальна кількість кольорів. |
| **Графіка** | `ford.jpg` | JPEG | 11,5 КБ | Логотип, мінімальна кількість кольорів. |
| **Графіка** | `ford.jpg` | JPEG | 11,5 КБ | Логотип, мінімальна кількість кольорів. |
| **Графіка** | `ford.jpg` | JPEG | 11,5 КБ | Логотип, мінімальна кількість кольорів. |
| **Графіка** | `ford.jpg` | JPEG | 11,5 КБ | Логотип, мінімальна кількість кольорів. |
| **Графіка** | `ford.jpg` | JPEG | 11,5 КБ | Логотип, мінімальна кількість кольорів. |

![Forest Original](images/forest.jpg)
![Screenshot Original](images/screenshot.png)
![Spotify Original](images/spotify.jpg)

## 3. Стиснення без втрати якості (Lossless)

PNG та WebP у режимі Lossless.  

### 3.1. Фотографія (Ліс)
![Forest Browser PNG](images/forest_browser_png.png)
![Forest WebP Lossless](images/forest_WebP.png)

### 3.2. Скріншот
![Screenshot Browser PNG](images/screenshot_browser_png.png)
![Screenshot WebP Lossless](images/screenshot_WebP.png)

### 3.3. Графіка (Spotify)
![Spotify Browser PNG](images/spotify_browser_png.png)
![Spotify WebP Lossless](images/spotify_WebP.png)

| Тип | Формат | Розмір |
| --- | --- | --- | --- |
| **Фотографія** | JPEG | 451 КБ |
| **Фотографія** | PNG | 145 КБ |
| **Скріншот** | JPEG | 11,5 КБ |
| **Скріншот** | JPEG | 11,5 КБ |
| **Графіка** | JPEG | 11,5 КБ |
| **Графіка** | JPEG | 11,5 КБ |

## 4. Стиснення з втратою якості (Lossy)

Дослідження форматів MozJPEG, WebP та AVIF на рівнях якості 100%, 75% та 50%.

### 4.1. Фотографія (Forest)
Найкращий результат показав **AVIF**.

**MozJPEG (100%, 75%, 50%)**
![MozJPEG 100](images/forest_MozJPEG_100.png)
![MozJPEG 75](images/forest_MozJPEG_75.png)
![MozJPEG 50](images/forest_MozJPEG_50.png)

**WebP (100%, 75%, 50%)**
![WebP 100](images/forest_WebP_100.png)
![WebP 75](images/forest_WebP_75.png)
![WebP 50](images/forest_WebP_50.png)

**AVIF (100%, 75%, 50%)**
![AVIF 100](images/forest_AVIF_100.png)
![AVIF 75](images/forest_AVIF_75.png)
![AVIF 50](images/forest_AVIF_50.png)
*Висновок по фото:* AVIF при якості 50% дав розмір **377 KB** при збереженні чудової візуальної якості.

---

### 4.2. Скріншот (Screenshot)
Для скріншотів формат JPEG (MozJPEG) показав себе найгірше через появу "шуму" навколо тексту.

**MozJPEG**
![MozJPEG 100](images/screenshot_MozJPEG_100.png)
![MozJPEG 75](images/screenshot_MozJPEG_75.png)
![MozJPEG 50](images/screenshot_MozJPEG_50.png)

**WebP**
![WebP 100](images/screenshot_WebP_100.png)
![WebP 75](images/screenshot_WebP_75.png)
![WebP 50](images/screenshot_WebP_50.png)

**AVIF**
![AVIF 100](images/screenshot_AVIF_100.png)
![AVIF 75](images/screenshot_AVIF_75.png)
![AVIF 50](images/screenshot_AVIF_50.png)
*Висновок по скріншоту:* AVIF 50% зменшив файл до **56.3 KB**.

---

### 4.3. Графіка (Spotify)
Тут було досягнуто найбільшого стиснення.

**MozJPEG**
![MozJPEG 100](images/spotify_MozJPEG_100.png)
![MozJPEG 75](images/spotify_MozJPEG_75.png)
![MozJPEG 50](images/spotify_MozJPEG_50.png)

**WebP**
![WebP 100](images/spotify_WebP_100.png)
![WebP 75](images/spotify_WebP_75.png)
![WebP 50](images/spotify_WebP_50.png)

**AVIF**
![AVIF 100](images/spotify_AVIF_100.png)
![AVIF 75](images/spotify_AVIF_75.png)
![AVIF 50](images/spotify_AVIF_50.png)
*Висновок по графіці:* Абсолютний рекорд у **AVIF 50% — всього 4.77 KB** (зменшення в 23 рази від оригіналу).

## 5. Оптимізація розміру (Resize)

Я адаптував зображення під різні екрани: Web (1200px), Mobile (600px) та Retina (2400px/2x).

### 5.1. Фотографія (Forest)
![Forest Mobile 600px](images/forest_1200.png)
![Forest Web 1200px](images/forest_600.png)
![Forest Retina 2400px](images/forest_2400.png)
*Результат:* Для мобільної версії (600px) файл займає всього **28 KB**.

### 5.2. Скріншот
![Screenshot Mobile 600px](images/screenshot_1200.png)
![Screenshot Web 1200px](images/screenshot_600.png)
![Screenshot Retina 2400px](images/screenshot_2400.png)

### 5.3. Графіка (Spotify)
![Spotify Mobile 600px](images/spotify_1200.png)
