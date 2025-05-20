
---

*Disclaimer: Ce script est fourni à titre éducatif uniquement. Le trading comporte des risques significatifs et ce script ne constitue pas un conseil financier.*# MarketControl Strategy

## Description
MarketControl est une stratégie de trading automatisée pour TradingView Pine Script v6. Cette stratégie a été spécialement optimisée pour les graphiques en Heiken Ashi. Elle analyse la structure du marché en calculant l'équilibre entre les forces acheteuses et vendeuses à travers une combinaison de facteurs techniques incluant:

- La taille et forme des bougies
- L'analyse des volumes
- La détection de formations chartistes (trois soldats blancs, trois corbeaux noirs, englobantes, marteaux, dojis)
- Les points de pivot (swing high/low)

## Fonctionnalités

### Indicateur de contrôle du marché
- Calcul en temps réel d'un score pour les acheteurs et les vendeurs
- Détection des changements de tendance
- Visualisation du contrôle du marché par changement de couleur de fond

### Signaux de trading
- Génération de signaux d'entrée en position long/short
- Détection de formations spécifiques pour renforcer les signaux
- Calcul automatique des niveaux de stop loss et take profit

### Filtres et gestion des risques
- Filtre horaire configurable (trading uniquement pendant les heures spécifiées)
- Stop loss basé sur les niveaux de pivot
- Ratio de take profit/stop loss personnalisable
- Fermeture automatique des positions lors d'une inversion de signal

### Visualisation
- Tableaux d'information affichant les scores actuels et la position
- Affichage des niveaux de stop loss et take profit
- Marquage des formations chartistes importantes
- Flèches indiquant les signaux d'entrée

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

## Installation

1. Ouvrez TradingView et accédez à l'éditeur Pine Script
2. Créez un nouveau script et collez le code
3. Sauvegardez et appliquez au graphique souhaité

## Résultats de Backtesting

La stratégie a démontré des performances solides en backtest sur le marché de l'or avec les résultats suivants:

- **Profit total**: +57,685 USD (+5.77%)
- **Réduction maximale des fonds**: 1,584.10 USD (0.16%)
- **Nombre total de transactions**: 511 (256 Long, 255 Short)
- **Transactions rentables**: 267 (52.25%)
- **Facteur de profit**: 3.282

### Détails des performances
- **Rentabilité en Long**: 51.95% (133 transactions gagnantes sur 256)
- **Rentabilité en Short**: 52.55% (134 transactions gagnantes sur 255)
- **P&L moyen par transaction**: 112.89 USD (0.04%)
- **Transaction gagnante moyenne**: 310.72 USD (0.10%)
- **Transaction perdante moyenne**: 110.39 USD (0.03%)

### Indicateurs de risque
- **Ratio de Sharpe**: 0.62
- **Ratio de Sortino**: 2.792
- **Facteur de profit global**: 3.282

Ces résultats montrent une stratégie équilibrée avec une bonne gestion du risque, comme en témoigne la faible réduction maximale des fonds (0.15%) par rapport au profit total (5.77%).

## Notes importantes

- Cette stratégie est spécialement optimisée pour fonctionner avec les graphiques en Heiken Ashi
- Elle est conçue pour fonctionner sur différents timeframes, mais ses performances peuvent varier selon l'instrument et l'horizon de trading
- Il est recommandé de tester la stratégie en backtest avant de l'utiliser en trading réel
- Les paramètres par défaut peuvent nécessiter un ajustement selon votre style de trading et les actifs négociés
