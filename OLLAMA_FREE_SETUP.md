# Codex - Fork Gratuit avec Ollama Neural Chat

Ce fork de Codex a été modifié pour fonctionner **100% gratuitement** avec **Ollama** et le modèle **Neural Chat** (open-source).

## 🎯 Différences avec l'original

- ✅ **Pas de clé API payante** - Pas besoin d'abonnement OpenAI
- ✅ **Modèle gratuit** - Neural Chat (open-source)
- ✅ **Exécution locale** - Tout fonctionne sur votre ordinateur
- ✅ **Pas de connexion ChatGPT requise** - Indépendant d'OpenAI

## 📋 Prérequis

1. **Installer Ollama** : https://ollama.ai
2. **Rust 1.83+** (pour compiler)
3. **Cargo** (gestionnaire de paquets Rust)

## 🚀 Installation et utilisation

### Étape 1 : Installer Ollama

```bash
# Linux/macOS
curl -fsSL https://ollama.ai/install.sh | sh

# Windows
# Téléchargez depuis https://ollama.ai/download
```

### Étape 2 : Télécharger le modèle Neural Chat

```bash
ollama pull neural-chat
```

Ce modèle (~4GB) est téléchargé automatiquement au premier lancement du projet.

### Étape 3 : Lancer Ollama

```bash
ollama serve
```

Cela démarre le serveur Ollama sur `http://localhost:11434`

### Étape 4 : Compiler et lancer Codex

```bash
cd codex-rs
cargo build --release
cargo run --release
```

## 📝 Utilisation

### Avec le modèle par défaut (Neural Chat)

```bash
codex --oss
```

### Avec un autre modèle Ollama

```bash
codex --oss -m mistral
# ou
codex --oss -m llama2
```

### Modèles Ollama recommandés (gratuits)

| Modèle | Taille | Vitesse | Qualité | Commande |
|--------|--------|---------|---------|----------|
| neural-chat | ~4GB | Rapide | Bon | `ollama pull neural-chat` |
| mistral | ~4GB | Très rapide | Bon | `ollama pull mistral` |
| llama2 | ~4GB | Moyen | Très bon | `ollama pull llama2` |
| dolphin-mixtral | ~26GB | Lent | Excellent | `ollama pull dolphin-mixtral` |

## ⚙️ Configuration

### Définir un modèle par défaut

Modifiez `codex-rs/ollama/src/lib.rs`, ligne 16 :

```rust
pub const DEFAULT_OSS_MODEL: &str = "neural-chat"; // Changez ici
```

### Configuration avancée

Créez un fichier `.env` dans le répertoire du projet :

```env
OLLAMA_HOST=http://localhost:11434
OLLAMA_MODEL=neural-chat
```

## 🔧 Troubleshooting

### Erreur : "Ollama not reachable"

```bash
# Vérifiez que Ollama est lancé
ollama serve

# Ou testez la connexion
curl http://localhost:11434/api/tags
```

### Erreur : "Model not found"

```bash
# Téléchargez le modèle manquant
ollama pull neural-chat
```

### Performance lente

- Utilisez `mistral` (plus léger et rapide)
- Augmentez la RAM disponible pour Ollama
- Utilisez une GPU compatible (CUDA/Metal)

## 📊 Performances

- **Neural Chat** : ~50 tokens/sec (CPU), ~200 tokens/sec (GPU)
- **Mistral** : ~80 tokens/sec (CPU), ~300 tokens/sec (GPU)
- Temps de réponse : 1-10 secondes (selon la complexité)

## 🔐 Respect de la vie privée

- ✅ **Aucune donnée envoyée à OpenAI**
- ✅ **Aucun tracking**
- ✅ **Données locales seulement**
- ✅ **Modèles open-source**

## 📚 Ressources

- [Documentation Ollama](https://github.com/ollama/ollama)
- [Liste des modèles disponibles](https://ollama.ai/library)
- [Repository original Codex](https://github.com/openai/codex)

## ⚖️ Licence

Ce fork maintient la licence Apache-2.0 de l'original.

Les modèles utilisés sont sous licence open-source (voir documentation Ollama).

---

**Créé pour une utilisation gratuite et locale de Codex** 🚀
