# MODIFICATIONS POUR OLLAMA NEURAL CHAT GRATUIT

## ✅ Changements effectués

### 1. Modèle par défaut changé
- **Avant** : `gpt-oss:20b` (ancien modèle)
- **Après** : `neural-chat` (gratuit, open-source)
- **Fichier** : `codex-rs/ollama/src/lib.rs` (ligne 16)

### 2. Dépendances
- ✅ Ollama support : **ACTIF**
- ✅ LM Studio support : **ACTIF**
- ⚠️ ChatGPT : **Encore disponible mais pas défaut**
- ⚠️ LM Studio : **Encore disponible**

## 🚀 Prochaines étapes pour VOUS

### Étape 1 : Installer Ollama
```bash
# macOS / Linux
curl -fsSL https://ollama.ai/install.sh | sh

# Ou visitez : https://ollama.ai/download
```

### Étape 2 : Télécharger Neural Chat
```bash
ollama pull neural-chat
```

### Étape 3 : Démarrer Ollama
```bash
ollama serve
```

### Étape 4 : Compiler Codex
```bash
cd codex-rs
cargo build --release
```

### Étape 5 : Lancer Codex
```bash
cargo run --release -- --oss
```

## 📝 Options d'utilisation

### Utiliser Neural Chat (défaut)
```bash
codex --oss
```

### Utiliser Mistral (plus rapide)
```bash
ollama pull mistral
codex --oss -m mistral
```

### Utiliser Llama2 (meilleure qualité)
```bash
ollama pull llama2
codex --oss -m llama2
```

## 🔧 Besoin de ChatGPT encore ?

Si vous voulez revenir à ChatGPT, définissez votre clé API :
```bash
export OPENAI_API_KEY="votre-clé-api"
codex  # Sans --oss
```

## 📊 Comparaison

| Aspect | Neural Chat | ChatGPT |
|--------|-------------|---------|
| **Coût** | Gratuit | Payant |
| **Local** | ✅ Oui | ❌ Non |
| **Vitesse** | Rapide | Variable |
| **Qualité** | Bonne | Excellente |
| **Confidentialité** | ✅ 100% local | ❌ Données envoyées |

## 💡 Conseils d'utilisation

1. **First launch** : Le modèle se télécharge automatiquement (~4GB)
2. **Performance** : GPU > CPU (install CUDA/Metal pour Ollama)
3. **RAM** : 8GB minimum, 16GB recommandé
4. **Vitesse** : ~50-100 tokens/sec en local

## 🐛 Problèmes courants

### Erreur "Ollama not reachable"
```bash
# Vérifiez qu'Ollama est lancé
ollama serve

# Dans un autre terminal
curl http://localhost:11434/api/tags
```

### Modèle pas trouvé
```bash
ollama pull neural-chat
```

### Trop lent
→ Utilisez `mistral` (plus léger)  
→ Installez une GPU compatible

## 📚 Ressources

- [Ollama GitHub](https://github.com/ollama/ollama)
- [Modèles disponibles](https://ollama.ai/library)
- [Codex Repo Original](https://github.com/openai/codex)

---

**Vous avez maintenant Codex GRATUIT et SANS LIMITE ! 🎉**
