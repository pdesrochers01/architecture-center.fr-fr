---
title: Modèles de gestion et de surveillance
titleSuffix: Cloud Design Patterns
description: Les applications cloud s’exécutent dans un centre de données distant où vous ne possédez pas de contrôle total sur l’infrastructure ou, dans certains cas, sur le système d’exploitation. Cela peut rendre la gestion et la surveillance plus difficile que pour un déploiement sur site. Les applications doivent exposer des informations de runtime que les administrateurs et opérateurs peuvent utiliser pour gérer et surveiller le système, ainsi que pour modifier les personnalisations et les exigences de l’entreprise, sans que l’application ne doive être arrêtée ou redéployée.
keywords: modèle de conception
author: dragon119
ms.date: 06/23/2017
ms.topic: design-pattern
ms.service: architecture-center
ms.subservice: cloud-fundamentals
ms.custom: seodec18
ms.openlocfilehash: 2b141a39b17f97ece011e93ca2f05cf5d2baeeea
ms.sourcegitcommit: 579c39ff4b776704ead17a006bf24cd4cdc65edd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/17/2019
ms.locfileid: "59641091"
---
# <a name="management-and-monitoring-patterns"></a>Modèles de gestion et de surveillance

Les applications cloud s’exécutent dans un centre de données distant où vous ne possédez pas de contrôle total sur l’infrastructure ou, dans certains cas, sur le système d’exploitation. Cela peut rendre la gestion et la surveillance plus difficile que pour un déploiement sur site. Les applications doivent exposer des informations de runtime que les administrateurs et opérateurs peuvent utiliser pour gérer et surveiller le système, ainsi que pour modifier les personnalisations et les exigences de l’entreprise, sans que l’application ne doive être arrêtée ou redéployée.

|                              Modèle                               |                                                              Résumé                                                              |
|--------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
|                   [Ambassadeur](../ambassador.md)                   |                 Créez des services d’assistance qui envoient des requêtes réseau pour le compte d’applications ou d’un service consommateur.                 |
|        [Couche de lutte contre la corruption](../anti-corruption-layer.md)        |                       Implémentez une couche de façade ou d’adaptateur entre une application moderne et un système hérité.                       |
| [Magasin de configurations externes](../external-configuration-store.md) |                Déplacez les informations de configuration depuis le package de déploiement d’application vers un emplacement centralisé.                |
|          [Agrégation de passerelle](../gateway-aggregation.md)          |                          Utilisez une passerelle pour agréger plusieurs requêtes individuelles dans une requête unique.                           |
|           [Déchargement de passerelle](../gateway-offloading.md)           |                              Déchargez des fonctionnalités de service partagé ou spécialisé sur un proxy de passerelle.                              |
|              [Routage de passerelle](../gateway-routing.md)              |                                   Acheminez les requêtes vers plusieurs services à l’aide d’un seul point de terminaison.                                    |
|   [Surveillance de point de terminaison d’intégrité](../health-endpoint-monitoring.md)   |   Implémentez des contrôles fonctionnels dans une application à laquelle des outils externes peuvent accéder par le biais de points de terminaison exposés à intervalles réguliers.    |
|                      [Sidecar](../sidecar.md)                      |         Déployez les composants d’une application sur un processus ou conteneur distinct pour fournir l’isolation et l’encapsulation.          |
|                    [Strangler](../strangler.md)                    | Faites migrer un système hérité de façon incrémentielle en remplaçant progressivement des parties spécifiques des fonctionnalités par de nouveaux services et applications. |
