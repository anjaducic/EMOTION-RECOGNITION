# Tema projekta: Prepoznavanje emocija spram facijalnih ekspresija  
### Tim: 
- Anja Dučić, E2 15/2024
- Anja Lovrić, E2 16/2024

### Kratak opis projekta:

Cilj ovog projekta je razvoj sistema za automatsko prepoznavanje emocija na osnovu facijalnih ekspresija prikazanih na slikama.
Skup podataka koji koristimo sastoji se od grayscale slika veličine 48x48 piksela, pri čemu je svaka slika označena kao jedna od sljedećih sedam emocija: angry, disgust, fear, happy, sad, surprise i neutral.

### Skup podataka:

Skup podataka sadrži grayscale slike lica sa izraženim emocijama čije su dimenzije 48×48 piksela.
Obuhvaćeno je ukupno 7 različitih emocija, a za svaku klasu dostupno je približno 4000 do 5000 slika.  
Link do skupa podataka: https://www.kaggle.com/datasets/jonathanoheix/face-expression-recognition-dataset/data

### Metodologija:

Za rješavanje zadatka radićemo transfer learning sljedećih CNN arhitektura:
- VGG
- ResNet
- MobileNet
- EfficientNet

Pored toga, implementiraćemo i jednostavnu CNN mrežu koja će služiti kao baseline za poređenje.

### Evaluacija:

Za evaluaciju koristićemo sljedeće metrike:
- tačnost
- preciznost
- odziv
- F1 score
- AUC score

U preuzetom skupu podataka postoje train i test podaci. Iz train skupa, koji je znatno obimniji, 15% podataka koristićemo kao validacioni skup.

### GitHub repozitorijum: https://github.com/anjaducic/EMOTION-RECOGNITION


