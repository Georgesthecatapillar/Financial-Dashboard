# Market Dashboard Skema

🚀 **[Accéder au dashboard en ligne](https://financial-dashboard-h7szhl7k7gbegyjbum2pic.streamlit.app/)**

Un dashboard interactif pour surveiller les régimes de marché multi-actifs en temps réel, construit avec Streamlit et des données réelles.

## 📊 Fonctionnalités

- **Surveillance du régime de marché** - Détection basée sur l'inversion de la courbe de rendement
- **Indicateurs clés** - Croissance, Inflation, Volatilité
- **Courbe de rendement des obligations** - Visualisation dynamique des rendements du Trésor américain
- **Dashboard Forex** - Suivi des paires de devises par région
- **Dashboard Indices** - Performance des indices boursiers
- **Analyse des corrélations** - Matrice de corrélation et corrélations roulantes
- **Comparaison de performance** - Rendements sur 1M, 3M, 6M, 1Y
- **Analyse du régime de marché** - Momentum des actions, corrélation obligations-actions, attentes d'inflation, etc.

## 🗂️ Structure des données

Les données sont chargées depuis des fichiers CSV :
- `Commodities_2Y.csv` - Prix des matières premières
- `Forex_2Y.csv` - Taux de change
- `Indices_2Y.csv` - Indices boursiers
- `FixedIncome_2Y.csv` - Rendements des obligations

**Format attendu :**
- Séparateur : `;` (point-virgule)
- Dates : `DD/MM/YYYY`
- Décimales : `,` (virgule)

## 📋 Prérequis

- Python 3.8+
- pip (gestionnaire de paquets Python)

## 🚀 Installation et lancement

### 1. Cloner le repository
```bash
git clone https://github.com/Georgesthecatapillar/Financial-Dashboard.git
cd Financial-Dashboard
```

### 2. Créer un environnement virtuel (optionnel mais recommandé)
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

### 3. Installer les dépendances
```bash
pip install -r requirements.txt
```

### 4. Lancer le dashboard
```bash
streamlit run main.py
```

L'app s'ouvrira automatiquement à `http://localhost:8501`

## 📱 Utilisation

### Filtrage des données
- **Sélection de la plage de dates** - Dans la barre latérale, choisissez votre plage de dates
- **Sélection des actifs** - Choisissez les actifs à afficher dans le graphique principal

### Sections du dashboard

#### Performance Metrics
Visualise la performance normalisée (base 100) des actifs sélectionnés sur la période choisie.

#### Latest Prices
Affiche les derniers prix et la variation quotidienne pour les actifs sélectionnés.

#### Bond Yield Curves
Sélectionnez une date pour visualiser la courbe de rendement du Trésor américain à cette date.

#### Forex Dashboard
Suivez les performances des paires de devises par région (USA, EMEA, Asia) avec différentes périodes.

#### Indices Dashboard
Visualisez la performance des indices boursiers majeurs normalisée à 100.

#### Asset Performance Comparison
Tableau comparatif des rendements sur différentes périodes (1M, 3M, 6M, 1Y).

#### Correlation Matrix
Calculez la matrice de corrélation entre les actifs sélectionnés.

#### Rolling Correlations
Analysez l'évolution de la corrélation entre deux actifs sur une fenêtre mobile.

#### Market Regime Analysis
Six indicateurs clés du régime de marché :
- Equity Momentum
- Bond-Equity Correlation
- Inflation Expectations
- Credit Spreads
- Dollar Strength
- Commodity Index

## 🔧 Configuration avancée

### Personnaliser les tickers
Modifiez le dictionnaire `TICKERS` dans `main.py` pour ajouter/retirer des actifs :

```python
TICKERS = {
    'Forex': [
        'USDCAD Curncy', 'EURUSD Curncy', ...
    ],
    'Commodities': [...],
    'Indices': [...],
    'Fixed Income': [...]
}
```

### Mettre à jour les URLs des données
Si vos fichiers CSV sont situés ailleurs, modifiez les URLs en haut de `main.py` :

```python
COMMODITIES_URL = "votre-url-ici"
FOREX_URL = "votre-url-ici"
```

## 📈 Mise à jour des données

Pour que le dashboard affiche les données les plus récentes :

1. **Mise à jour manuelle** : Remplacez les fichiers CSV localement et poussez sur GitHub
2. **Mise à jour automatique** : Configurez GitHub Actions pour mettre à jour les données automatiquement

## 🤝 Contribution

Les contributions sont bienvenues ! N'hésitez pas à :
- Signaler des bugs
- Proposer des améliorations
- Ajouter de nouvelles fonctionnalité
