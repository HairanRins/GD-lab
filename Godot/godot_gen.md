# Godot Engine 

Voici les **bases essentielles à connaître pour bien démarrer avec Godot Engine**, un moteur de jeu open-source particulièrement apprécié pour sa légèreté, sa flexibilité et sa courbe d’apprentissage raisonnable :

---

### 🎮 1. **Scènes et nœuds**

* **Tout dans Godot est une scène**, et chaque scène est composée de **nœuds (nodes)**.
* Une scène peut être un personnage, un objet, un niveau, etc.
* Chaque nœud a un **type spécifique** : `Sprite2D`, `CollisionShape2D`, `Label`, `AnimationPlayer`, `Camera2D`, etc.
* Les scènes peuvent être **imbriquées** (tu peux instancier une scène dans une autre).

---

### 📜 2. **GDScript**

* Le langage principal de Godot, inspiré de Python : facile à apprendre et très lisible.
* Tu peux aussi utiliser C#, C++ ou VisualScript, mais GDScript reste le plus courant.
* Exemple simple :

  ```gdscript
  func _ready():
      print("Hello Godot!")
  ```

---

### 🧠 3. **Cycle de vie des scripts**

* `func _ready()` : appelé quand le nœud est prêt.
* `func _process(delta)` : appelé à chaque frame.
* `func _physics_process(delta)` : appelé à chaque frame physique (utile pour le mouvement).

---

### 🎯 4. **Système d'entrée (Input)**

* Gère les touches, clics souris, manettes, etc.
* Utilise `Input.is_action_pressed("ui_right")` pour détecter les entrées.
* Les actions sont définies dans **Project > Project Settings > Input Map**.

---

### 📦 5. **Ressources et instanciation**

* Les scènes, scripts, images, sons, animations sont tous des **ressources**.
* Tu peux **instancier** une scène depuis le code :

  ```gdscript
  var enemy = preload("res://Enemy.tscn").instantiate()
  add_child(enemy)
  ```

---

### 💥 6. **Physique et collisions**

* `Area2D`, `CollisionShape2D`, `RigidBody2D`, `KinematicBody2D` (remplacé par `CharacterBody2D` depuis Godot 4).
* Pour les jeux avec physique : détecter les collisions, appliquer des forces, gérer les contacts.

---

### 🎨 7. **Animation et UI**

* `AnimationPlayer` pour animer les propriétés de nœuds.
* `CanvasLayer` pour des éléments de HUD.
* `Control` nodes pour créer des interfaces utilisateur (`Button`, `Label`, `VBoxContainer`, etc.).

---

### 🗂 8. **Organisation et export**

* Structure propre du projet (dossiers clairs : `scenes/`, `scripts/`, `assets/`, etc.).
* Exports multiplateformes : Windows, Android, Web, etc.

---

### 🔄 9. **Signal et communication entre nœuds**

* Les **signals** sont comme des événements (ex : un bouton cliqué).
* Tu peux les connecter dans l’éditeur ou par script :

  ```gdscript
  button.pressed.connect(_on_button_pressed)
  ```

---

### 📘 10. **Documentation & communauté**

* [https://docs.godotengine.org/](https://docs.godotengine.org/) est très bien faite.
* Une grande communauté sur Reddit, Discord, et GitHub.

---
