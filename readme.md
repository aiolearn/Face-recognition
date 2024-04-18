# face recognition

We wrote a face recognition project in this program

## Modules

```python
import face_recognition as fr
import cv2
import numpy as np
```

## Usage

Upload photo

```python
image = fr.load_image_file("nima.jpg")
```

Find the face

```python
locate = fr.face_locations(image)
locate[0][0]
```

Convert photo to RGB

```python
image2 = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

image2 = cv2.rectangle(image2,(locate[0][3],locate[0][0]),(locate[0][1],locate[0][2]),(255,0,0),4)

cv2.imshow('image', image2)
cv2.waitKey(0)
cv2.destroyAllWindows()

image2.shape
```

This code extracts face equations in the image using the face_recognition library.

```python
sabte_surat = fr.face_encodings(image)[0]

sabte_surat
```

Loading the second photo

```python
imagetest = fr.load_image_file('farzan.jpg')

imagetest_encode = fr.face_encodings(imagetest)[0]
```

Here the characteristics of two faces are compared

```python
result = fr.compare_faces([sabte_surat], imagetest_encode)
print(result)
```

<h1> The sixth session of the practical machine learning project </h1>

open camera

```python
cap = cv2.VideoCapture(0)
```

load pictures

```puthon
image_ati = fr.load_image_file("biden.jpg")
sabte_surat2 = fr.face_encodings(image_ati)[0]

image_eri = fr.load_image_file("obama.jpg")
sabte_surat3 = fr.face_encodings(image_eri)[0]
```

In order to take a video, we put it inside the loop

```python
cap = cv2.VideoCapture(0)

while True:

    _,img = cap.read()


    img2 = cv2.cvtColor(img,cv2.COLOR_BGR2RGB)
    locate = fr.face_locations(img2)
    
    
    if len(locate) > 0:
        img = cv2.rectangle(img,(locate[0][3],locate[0][0]),(locate[0][1],locate[0][2]),(255,0,0),2)

        
        encode = fr.face_encodings(img2)

        result = fr.compare_faces([sabte_surat , sabte_surat2 , sabte_surat3], encode[0])
        
        if result[0] == True:
            cv2.putText(img, "mamasi",(locate[0][3] + 6, locate[0][0] - 6), cv2.FONT_HERSHEY_SIMPLEX, 1.0, (255,0,0),2)
        elif result[1] == True:
            cv2.putText(img, "atefeh",(locate[0][3] + 6, locate[0][0] - 6), cv2.FONT_HERSHEY_SIMPLEX, 1.0, (255,0,0),2)
        elif result[2] == True:
            cv2.putText(img, "erfaneh",(locate[0][3] + 6, locate[0][0] - 6), cv2.FONT_HERSHEY_SIMPLEX, 1.0, (255,0,0),2)
        else:
            cv2.putText(img, "unknown",(locate[0][3] + 6, locate[0][0] - 6), cv2.FONT_HERSHEY_SIMPLEX, 1.0, (255,0,0),2)


    cv2.imshow('img',img)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break




cap.release()
cv2.destroyAllWindows()
```

## Result

This project was written by Majid Tajanjari and the Aiolearn team, and we need your support!❤️

# تشخیص چهره

ما در این برنامه پروژه تشخیص چهره نوشتیم

## ماژول

```python
import face_recognition as fr
import cv2
import numpy as np
```

## نحوه استفاده

آپلود عکس

```python
image = fr.load_image_file("nima.jpg")
```

پیدا کردن چهره

```python
locate = fr.face_locations(image)
locate[0][0]
```

RGB تبدیل عکس به 

```python
image2 = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

image2 = cv2.rectangle(image2,(locate[0][3],locate[0][0]),(locate[0][1],locate[0][2]),(255,0,0),4)

cv2.imshow('image', image2)
cv2.waitKey(0)
cv2.destroyAllWindows()

image2.shape
```

این کد معادلات چهره در تصویر را با استفاده از کتابخانه face_recognition استخراج می کند.

```python
sabte_surat = fr.face_encodings(image)[0]

sabte_surat
```

آپلود دومین عکس

```python
imagetest = fr.load_image_file('farzan.jpg')

imagetest_encode = fr.face_encodings(imagetest)[0]
```

در اینجا ویژگی های دو چهره مقایسه می شود

```python
result = fr.compare_faces([sabte_surat], imagetest_encode)
print(result)
```

<h1> جلسه ششم پروژه عملی یادگیری ماشین </h1>

باز کردن دوربین

```python
cap = cv2.VideoCapture(0)
```

لود کردن عکس

```puthon
image_ati = fr.load_image_file("biden.jpg")
sabte_surat2 = fr.face_encodings(image_ati)[0]

image_eri = fr.load_image_file("obama.jpg")
sabte_surat3 = fr.face_encodings(image_eri)[0]
```

برای گرفتن فیلم، آن را داخل حلقه قرار می دهیم

```python
cap = cv2.VideoCapture(0)

while True:

    _,img = cap.read()


    img2 = cv2.cvtColor(img,cv2.COLOR_BGR2RGB)
    locate = fr.face_locations(img2)
    
    
    if len(locate) > 0:
        img = cv2.rectangle(img,(locate[0][3],locate[0][0]),(locate[0][1],locate[0][2]),(255,0,0),2)

        
        encode = fr.face_encodings(img2)

        result = fr.compare_faces([sabte_surat , sabte_surat2 , sabte_surat3], encode[0])
        
        if result[0] == True:
            cv2.putText(img, "mamasi",(locate[0][3] + 6, locate[0][0] - 6), cv2.FONT_HERSHEY_SIMPLEX, 1.0, (255,0,0),2)
        elif result[1] == True:
            cv2.putText(img, "atefeh",(locate[0][3] + 6, locate[0][0] - 6), cv2.FONT_HERSHEY_SIMPLEX, 1.0, (255,0,0),2)
        elif result[2] == True:
            cv2.putText(img, "erfaneh",(locate[0][3] + 6, locate[0][0] - 6), cv2.FONT_HERSHEY_SIMPLEX, 1.0, (255,0,0),2)
        else:
            cv2.putText(img, "unknown",(locate[0][3] + 6, locate[0][0] - 6), cv2.FONT_HERSHEY_SIMPLEX, 1.0, (255,0,0),2)


    cv2.imshow('img',img)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break




cap.release()
cv2.destroyAllWindows()
```

## نتیجه

این پروژه توسط مجید تجن جاری و تیم Aiolearn نوشته شده است و ما به حمایت شما نیازمندیم!❤️