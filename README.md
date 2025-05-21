# MarketControl Strategy

## Description
MarketControl est une stratégie de trading automatisée pour TradingView Pine Script v6. Elle analyse la structure du marché en calculant l'équilibre entre les forces acheteuses et vendeuses à travers une combinaison de facteurs techniques incluant:

- La taille et forme des bougies
- L'analyse des volumes
- La détection de formations chartistes (trois soldats blancs, trois corbeaux noirs, englobantes, marteaux, dojis)
- Les points de pivot (swing high/low)
- L'analyse de la tendance via moyenne mobile et calcul de pente

## Fonctionnalités

### Indicateur de contrôle du marché
- Calcul en temps réel d'un score pour les acheteurs et les vendeurs
- Détection des changements de tendance
- Visualisation du contrôle du marché par changement de couleur de fond
- Identification de formations chartistes spécifiques (bonus de score)

### Signaux de trading
- Génération de signaux d'entrée en position long/short
- Détection de formations spécifiques pour renforcer les signaux
- Calcul automatique des niveaux de stop loss et take profit
- Fermeture automatique des positions quand le signal s'inverse

### Filtres et gestion des risques
- Filtre horaire configurable (trading uniquement pendant les heures spécifiées)
- Filtre de tendance basé sur la pente de la moyenne mobile
- Filtre de position du prix par rapport à la moyenne mobile
- Stop loss basé sur les niveaux de pivot
- Ratio de take profit/stop loss personnalisable
- Fermeture automatique des positions lors d'une inversion de signal

### Visualisation
- Tableaux d'information affichant les scores actuels et la position
- Affichage des niveaux de stop loss et take profit
- Marquage des formations chartistes importantes
- Flèches indiquant les signaux d'entrée
- Affichage de la moyenne mobile avec coloration selon la pente
- Affichage des points de pivot détectés
- Table d'information sur la pente de la moyenne mobile et la position du prix

## Comment utiliser

1. Copiez le code Pine Script dans l'éditeur Pine Script de TradingView
2. Ajustez les paramètres selon vos préférences:
   - Paramètres de l'indicateur (période d'analyse, poids des facteurs)
   - Paramètres de trading (filtres horaires, ratio TP/SL)
3. Appliquez le script à votre graphique
4. Activez la stratégie dans l'onglet "Strategy Tester" pour tester ou trader en live

## Paramètres personnalisables

### Indicateur
- `lookbackPeriod`: Période d'analyse pour le calcul des scores (défaut: 2)
- `volumeWeight`: Importance du volume dans le calcul (défaut: 2.5)
- `bodySizeWeight`: Importance de la taille du corps des bougies (défaut: 2)
- `wickWeight`: Importance des mèches des bougies (défaut: 0.8)
- `closePosWeight`: Importance de la position de clôture (défaut: 2)

### Trading
- `startHour` / `endHour`: Plage horaire pour le trading (UTC+3)
- `timeFrameFilter`: Activer/désactiver le filtre horaire
- `swingPeriod`: Période pour détecter les swing high/low (défaut: 5)
- `tpRatio`: Ratio take profit / stop loss (défaut: 1.5)

### Filtre de tendance
- `maPeriod`: Période de la moyenne mobile (défaut: 50)
- `slopePeriod`: Période de calcul de la pente (défaut: 14)
- `minAbsSlope`: Pente minimale en % (défaut: 0.15)
- `useMAFilter`: Activer/désactiver le filtre de pente
- `useMACrossFilter`: Activer/désactiver le filtre de position prix/MA

## 📊 Paramètres Optimaux – Stratégie de Trading

Ces réglages ont été testés et optimisés pour un meilleur rendement.

### ⚙️ Gestion des Risques

| Paramètre                 | Valeur |
|--------------------------|--------|
| Période pour Swing High/Low | `5`    |
| Ratio TP/SL              | `2`    |

---

### 📈 Filtres de Tendance

| Paramètre                         | Valeur  |
|----------------------------------|---------|
| Période de la Moyenne Mobile     | `11`    |
| Période de calcul de pente       | `14`    |
| Pente minimale (%)               | `0.006` |
| Activer le filtre de pente       | ✅       |
| Activer le filtre position prix/MA | ✅       |

---

### 🕯️ Pondération des Composantes du Score des Bougies

| Composante                     | Poids  |
|--------------------------------|--------|
| Importance du volume           | `2.5`  |
| Importance de la taille du corps | `2`    |
| Importance des mèches          | `1.3`  |
| Importance de la position de clôture | `2`    |

---

### ⏰ Filtres Temporels

| Paramètre                | Valeur |
|--------------------------|--------|
| Activer le filtre horaire | ❌     |
| Heure de début (UTC+3)   | `9`    |
| Heure de fin (UTC+3)     | `19`   |
  
## Installation

1. Ouvrez TradingView et accédez à l'éditeur Pine Script
2. Créez un nouveau script et collez le code
3. Sauvegardez et appliquez au graphique souhaité

## Résultats de Backtesting

La stratégie a démontré des performances exceptionnelles en backtest sur le graphique en chandelier japonais de 4h des contrats à terme sur OR avec les résultats suivants:

- **Profit total**: +2 315 540 USD (+226,20%)
- **Réduction maximale des fonds**: 215 340 USD (6,59%)
- **Nombre total de transactions**: 496
- **Transactions rentables**: 39,52% (196/300)
- **Facteur de profit**: 1,982

### Détails des performances
- **Profit net total**: +2 238 140 USD (+223,81%)
- **Profit net en Long**: +1 694 800 USD (+169,48%)
- **Profit net en Short**: +543 340 USD (+54,33%)
- **Gross Profit**: 4 518 160 USD (451,82%)
- **Perte brute**: 2 280 020 USD (228,00%)
- **Commissions payées**: 19 860 USD

### Indicateurs de risque
- **Ratio de Sharpe**: 0,852
- **Ratio de Sortino**: 3,94
- **Facteur de profit global**: 1,982
- **Facteur de profit en Long**: 2,733
- **Facteur de profit en Short**: 1,417
- **Hausse maximale des fonds propres**: 2 349 740 USD (70,23%)
- **Rendement du Buy & Hold**: +759 550 USD (+75,96%)

Ces résultats montrent une stratégie très performante avec une excellente gestion du risque, comme en témoigne la faible réduction maximale des fonds (6,59%) par rapport au profit total (226,20%).

## Notes importantes

- Elle est conçue pour fonctionner sur différents timeframes, mais ses performances peuvent varier selon l'instrument et l'horizon de trading
- Il est recommandé de tester la stratégie en backtest avant de l'utiliser en trading réel
- Les paramètres par défaut peuvent nécessiter un ajustement selon votre style de trading et les actifs négociés
- Le filtre de tendance améliore significativement la qualité des signaux en éliminant les entrées en marché sans direction claire
- Le filtre de position prix/MA évite les trades contre-tendance

*Disclaimer: Ce script est fourni à titre éducatif uniquement. Le trading comporte des risques significatifs et ce script ne constitue pas un conseil financier.*

