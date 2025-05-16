# ESP32 - Affichage 7 Segments et Lecture Potentiomètre

Ce projet a pour objectif de démontrer l'utilisation d'un **afficheur 7 segments 4 digits** et d'un **potentiomètre** sur une carte **ESP32**, en utilisant **FreeRTOS**. Il s'agit d'un exemple d'apprentissage de l'ESP-IDF (framework officiel d'ESP32).

## 🎯 Objectifs pédagogiques

- Contrôler un afficheur 7 segments (4 chiffres).
- Lire la valeur d’un potentiomètre via l’ADC.
- Gérer un bouton poussoir avec effet d'appui.
- Créer des tâches FreeRTOS pour séparer les responsabilités.

---

## ⚙️ Matériel utilisé

- ESP32 DevKit (ou équivalent)
- Afficheur 7 segments à 4 chiffres (multiplexé)
- Potentiomètre (connecté à une entrée analogique)
- Bouton poussoir (pull-up interne)
- LED (intégrée ou externe, reliée à GPIO 2)

---

## 📌 Fonctionnalités

### 🖥️ Affichage
- L’afficheur affiche le nombre **1234** de manière constante.
- L’intensité de l’affichage est contrôlée en temps réel par un **potentiomètre** (ADC).

### 🔘 Bouton
- Un bouton poussoir est lu via une tâche dédiée.
- Chaque appui incrémente un compteur affiché dans les logs (ESP_LOGI).
- Une **LED** reflète l’état du bouton (ON quand bouton relâché, OFF quand appuyé).

---

## 🧪 Détails techniques

- Le **potentiomètre** est connecté au canal ADC1_CHANNEL_6 (GPIO34 par défaut).
- Le **bouton poussoir** est connecté au GPIO32.
- La **LED** est connectée au GPIO2.
- Utilisation d’une **tâche FreeRTOS par fonctionnalité** :
  - `display_task` : mise à jour de l'affichage.
  - `button_task` : lecture du bouton et contrôle LED.
- Le fichier `display.h` doit contenir les fonctions :
  - `display_init()`
  - `display_set_value(int value, int brightness)`

---

## 🚀 Démarrage rapide

1. Cloner le dépôt.
2. Ajouter/implémenter les fonctions dans `display.h/.c` selon le matériel utilisé.
3. Compiler et flasher avec l’ESP-IDF :
   ```bash
   idf.py build
   idf.py flash monitor
