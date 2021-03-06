---
title: 'Framework d’adoption du cloud : Collecter des données d’inventaire pour un patrimoine numérique'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Description du processus de collecte des données d’inventaire pour un patrimoine numérique
author: BrianBlanchard
ms.date: 12/10/2018
ms.topic: guide
ms.service: architecture-center
ms.subservice: enterprise-cloud-adoption
ms.openlocfilehash: 0c68ff1e5ff51395698d37fb9b59c7a76c9479b7
ms.sourcegitcommit: c053e6edb429299a0ad9b327888d596c48859d4a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/20/2019
ms.locfileid: "58242550"
---
# <a name="gather-inventory-data-for-a-digital-estate"></a>Collecter des données d’inventaire pour un patrimoine numérique

Le développement d’un inventaire est la première étape de [planification du patrimoine numérique](overview.md). Au cours de ce processus, des ressources informatiques prenant en charge des fonctions métier spécifiques sont collectées en vue d’être analysées et rationalisées. Cet article part du principe qu’une analyse ascendante est plus appropriée pour la planification des besoins. Pour plus d’informations, consultez [Approches de la planification du patrimoine numérique](./approach.md).

## <a name="take-inventory-of-a-digital-estate"></a>Inventaire du patrimoine numérique

L’inventaire d’un patrimoine numérique est différent selon la transformation numérique souhaitée et le processus de transformation qui lui est associé.

- **Transformation opérationnelle**. Lors d’une transformation opérationnelle, il est souvent recommandé que l’inventaire soit réalisé à l’aide d’outils d’analyse qui peuvent créer une liste centralisée de tous les serveurs et de toutes les machines virtuelles. Certains outils peuvent également créer des mappages et des dépendances réseau, qui aident à définir l’alignement des charges de travail.

- **Transformation incrémentielle**. L’inventaire d’une transformation incrémentielle commence par le client. Le mappage de l’expérience client du début à la fin est un bon point de départ. L’alignement de ce mappage sur les applications, les API, les données et autres ressources permet de créer un inventaire détaillé pour l’analyse.

- **Transformation disruptive**. La transformation disruptive concerne un produit ou un service. Pour ce type de transformation, l’inventaire comprend un mappage des opportunités de disruption du marché ainsi que des fonctionnalités nécessaires.

## <a name="accuracy-and-completeness-of-an-inventory"></a>Exactitude et complétude de l’inventaire

Un inventaire est rarement complet après sa première itération. Il est vivement recommandé que les différents membres de l’équipe chargée des stratégies cloud alignent les parties prenantes et les utilisateurs avancés afin de valider l’inventaire. Lorsque cela est possible, d’autres outils, comme l’analyse du réseau et des dépendances, peuvent être utilisés pour identifier les ressources qui reçoivent du trafic, mais qui ne figurent pas dans l’inventaire.

## <a name="next-steps"></a>Étapes suivantes

Une fois l’inventaire compilé et validé, il peut être rationalisé. La rationalisation de l’inventaire est l’étape qui suit dans la planification du patrimoine numérique.

> [!div class="nextstepaction"]
> [Rationaliser le patrimoine numérique](rationalize.md)