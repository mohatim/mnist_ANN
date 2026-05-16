# MNIST - Classification par réseau de neurones (ANN)

Classification des chiffres manuscrits du dataset MNIST avec des réseaux de neurones denses (ANN) en TensorFlow/Keras.

## Dataset

- **60 000** images d'entraînement, **10 000** images de test
- Images en niveaux de gris de **28×28 pixels** (valeurs 0–255)
- **10 classes** : chiffres de 0 à 9

## Pré-traitement

- Aplatissement des matrices 28×28 en vecteurs de 784 pixels
- Normalisation des valeurs entre 0 et 1
- Encodage one-hot des étiquettes

## Architectures testées

### Modèle 1 — 2 couches
| Couche | Neurones | Activation |
|--------|----------|------------|
| Entrée / Dense | 784 | ReLU |
| Sortie | 10 | Softmax |

**Paramètres totaux : 623 290**

### Modèle 2 — 4 couches
| Couche | Neurones | Activation |
|--------|----------|------------|
| Dense 1 | 784 | ReLU |
| Dense 2 | 300 | ReLU |
| Dense 3 | 100 | ReLU |
| Sortie | 10 | Softmax |

**Paramètres totaux : 882 050**

## Entraînement

- **Optimiseur** : Adam
- **Fonction de perte** : Categorical Crossentropy
- **Epochs** : 10
- **Batch size** : 200

## Résultats

| Modèle | Précision (test) |
|--------|-----------------|
| Modèle 1 (2 couches) | ~98.2% |
| Modèle 2 (4 couches) | ~98.0% |

Les deux modèles atteignent ~98% de précision. L'ajout de couches supplémentaires n'améliore pas significativement les performances sur MNIST. Un léger surapprentissage apparaît à partir de l'époque 8.

## Stack

- Python
- TensorFlow / Keras
- NumPy
- Matplotlib
