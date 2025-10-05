# 🎭 Prepoznavanje emocija na osnovu facijalnih ekspresija primenom konvolucionih neuronskih mreža

## 🎯 Cilj projekta

Cilj ovog projekta je razvoj sistema za **automatsko prepoznavanje emocija** na osnovu facijalnih ekspresija prikazanih na slikama.  
Skup podataka koji koristimo sastoji se od **grayscale slika veličine 48×48 piksela**, pri čemu je svaka slika označena kao jedna od sledećih sedam emocija:  
**angry**, **disgust**, **fear**, **happy**, **sad**, **surprise** i **neutral**.  

---

## 📎 Uputstvo za početak

U folderu **`EMOTION-RECOGNITION/`** nalaze se Jupyter Notebook fajlovi sa implementacijama različitih modela:  
- Posebni notebook-ovi za **ResNet50** i **MobileNetV2** modele, organizovani odvojeno u fajlovima redom **`resnet.ipynb`** i **`mobilenet.ipynb`**. Rezultati za ResNet i MobileNet prikazani su direktno unutar Jupyter notebook fajlova.
- U podfolderu **`vgg_inception/`** nalazi se **`emotion_recognition.ipynb`** sa **Baseline implementacijama**,  **VGG19** i **InceptionV3** modelima. Svi izveštaji o rezultatima ovih modela modela nalaze se u **`.txt fajlovima`** u okviru foldera **`vgg_inception/`**.


## 🚀 Instalacija i pokretanje

1. Kloniraj repozitorijum:

```bash
git clone https://github.com/anjaducic/EMOTION-RECOGNITION.git
cd EMOTION-RECOGNITION
``` 
   
2. Instaliraj potrebne biblioteke (nije korišćeno virtuelno okruženje):

  ```bash
  pip install tensorflow keras numpy matplotlib kagglehub scikit-learn seaborn
  ```

3. Pokreni željeni Jupyter notebook, na primer:

```bash
jupyter notebook emotion_recognition.ipynb
```

## 🧠 Skup podataka

Za treniranje i evaluaciju modela korišćen je **Face Expression Recognition Dataset**
 sa platforme Kaggle. Dataset je dostupan [ovde](https://www.kaggle.com/datasets/jonathanoheix/face-expression-recognition-dataset/data).

Skup podataka sadrži grayscale slike lica sa izraženim emocijama čije su dimenzije 48×48 piksela.
Obuhvaćeno je ukupno 7 različitih emocija, a za svaku klasu dostupno je približno 5000–6000 slika
(osim disgust, koja ima oko 500, dok happy ima oko 8000).

U okviru skupa postoje train i test podaci, pri čemu se 20% train skupa koristi za validaciju.
Podaci se automatski preuzimaju tokom izvršavanja koda pomoću biblioteke kagglehub.
Podaci su pretprocesirani kako bi bili spremni za treniranje i evaluaciju modela.

## 🧩 Modeli i arhitekture

Za rešavanje zadatka korišćen je transfer learning i fine-tuning sledećih konvolucionih neuronskih mreža:
- VGG19	
- InceptionV3
- ResNet50	
- MobileNetV2
  
Pored toga, implementirane su i dve osnovne CNN mreže (baseline modeli) koje se treniraju od nule i služe za poređenje:
- Baseline CNN (grayscale) – koristi slike u sivim tonovima kao ulaz.
- Baseline CNN (RGB) – koristi trokanalne (RGB) slike kao ulaz.


## 📊 Metrike evaluacije

Za procenu performansi modela korišćene su sledeće metrike:
- Tačnost (Accuracy)
- Preciznost (Precision)
- Odziv (Recall)
- F1 skor (F1 Score)
- AUC skor (Area Under Curve)


## 📈 Primer rezultata (Baseline grayscale)
```txt
=== Eval results (from model.evaluate - loss, accuracy, precision, recall, AUC) ===
[1.029132604598999, 0.6164732575416565, 0.7502252459526062, 0.47141239047050476, 0.91164630651474]

=== Global metrics ===
Accuracy: 0.6165
Macro Precision: 0.5984
Weighted Precision: 0.6175
Macro Recall: 0.6082
Weighted Recall: 0.6165
Macro F1: 0.6000
Weighted F1: 0.6140
AUC (OVR): 0.8917

=== Per-class metrics ===
              precision    recall  f1-score   support

           0     0.4995    0.5115    0.5054       960
           1     0.6031    0.7117    0.6529       111
           2     0.4867    0.3585    0.4129      1018
           3     0.8425    0.8323    0.8374      1825
           4     0.5045    0.6447    0.5661      1216
           5     0.5037    0.4759    0.4894      1139
           6     0.7490    0.7227    0.7356       797

    accuracy                         0.6165      7066
   macro avg     0.5984    0.6082    0.6000      7066
weighted avg     0.6175    0.6165    0.6140      7066
```



## Tim: 
- Anja Dučić, E2 15/2024
- Anja Lovrić, E2 16/2024


