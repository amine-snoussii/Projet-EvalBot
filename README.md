# 🤖 Patrouille-Bot — Robot Autonome de Surveillance

Projet réalisé en binôme dans le cadre du module **Programmation et Systèmes à base de Microprocesseurs** à l'ESIEE Paris (Novembre 2025).

![Demo Patrouille-Bot](./VidoEvalBot-ezgif.com-optimize.gif)

## 📋 Description

Le Patrouille-Bot est un robot autonome de surveillance urbaine programmé en **assembleur ARM Cortex-M3** sur la plateforme **EVALBOT de Texas Instruments (Stellaris LM3S9B92)**, via Keil µVision.

Le robot simule une patrouille nocturne : il avance en clignotant ses LEDs, détecte les obstacles via ses bumpers et adapte sa trajectoire en temps réel.

## ⚙️ Fonctionnement

- **Démarrage** : appui sur SW1 → les moteurs s'activent, les LEDs clignotent
- **Obstacle à gauche** : rotation à droite
- **Obstacle à droite** : rotation à gauche  
- **Collision frontale** : recul + rotation
- **4ème collision frontale** : mode **Forcing** — le robot accélère pour forcer le passage
- **Arrêt** : appui sur SW2

## 🗂️ Architecture du code

Le code est divisé en 5 fichiers modulaires :

| Fichier | Rôle |
|---|---|
| `Main.s` | Logique principale — boucles PAUSE / PLAY / FORCING |
| `Moteur.s` | 14 routines de contrôle des moteurs (PWM) |
| `Leds.s` | 6 routines de gestion des LEDs |
| `Bumper.s` | 4 routines de lecture des capteurs |
| `Switch.s` | 3 routines de lecture des boutons |

## 🛠️ Stack technique

- Assembleur ARM Cortex-M3
- Texas Instruments EVALBOT (Stellaris LM3S9B92)
- Keil µVision
- Périphériques : LEDs, Bumpers, Switchs, Moteurs (PWM)


## 📄 Rapport complet

[📎 Voir le rapport du projet (PDF)](./Rapport-Projet-G5s07_IGI-3001.pdf)
