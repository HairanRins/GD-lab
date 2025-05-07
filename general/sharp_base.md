# C# Base

Voici les **bases essentielles du C# à connaître pour le développement de jeux vidéo**, notamment avec Unity (le moteur le plus courant pour C#) :

---

### 1. **Syntaxe de base**

* Déclaration de variables :

  ```csharp
  int score = 0;
  float speed = 5.0f;
  bool isJumping = false;
  string playerName = "Alex";
  ```

* Conditions :

  ```csharp
  if (score > 10) { /* faire quelque chose */ }
  else if (score == 10) { /* autre chose */ }
  else { /* encore autre chose */ }
  ```

* Boucles :

  ```csharp
  for (int i = 0; i < 10; i++) { /* boucle */ }
  while (isJumping) { /* boucle tant que */ }
  ```

---

### 2. **Structures de base**

* Fonctions :

  ```csharp
  void Jump() {
      Debug.Log("Le joueur saute !");
  }
  ```

* Classes et objets :

  ```csharp
  public class Player {
      public string name;
      public int health;

      public void TakeDamage(int amount) {
          health -= amount;
      }
  }
  ```

* Constructeurs :

  ```csharp
  public Player(string playerName) {
      name = playerName;
      health = 100;
  }
  ```

---

### 3. **Spécificités Unity / GameDev**

* **MonoBehaviour** : Classe de base pour les scripts Unity.

  ```csharp
  public class PlayerController : MonoBehaviour {
      void Start() {
          // S’exécute une seule fois au début
      }

      void Update() {
          // S’exécute à chaque frame
      }
  }
  ```

* **Transformations** :

  ```csharp
  transform.position += new Vector3(1, 0, 0) * Time.deltaTime;
  ```

* **Entrées utilisateur** :

  ```csharp
  if (Input.GetKeyDown(KeyCode.Space)) {
      Jump();
  }
  ```

---

### 4. **Physique et collisions**

* Détection de collisions :

  ```csharp
  void OnCollisionEnter(Collision collision) {
      Debug.Log("Collision avec " + collision.gameObject.name);
  }
  ```

* Rigidbody (pour les objets physiques) :

  ```csharp
  Rigidbody rb = GetComponent<Rigidbody>();
  rb.AddForce(Vector3.up * 5, ForceMode.Impulse);
  ```

---

### 5. **Outils importants**

* **ScriptableObjects** : pour stocker des données (comme des profils d'ennemis).
* **Coroutines** :

  ```csharp
  IEnumerator WaitAndShoot() {
      yield return new WaitForSeconds(1f);
      Shoot();
  }
  ```

---

### 6. **Bonnes pratiques**

* Garder chaque script centré sur une responsabilité (principe SRP).
* Utiliser des noms explicites et lisibles.
* Séparer logique et affichage si possible.
* Éviter les références directes en dur (utiliser `SerializeField` et `public` si besoin).
