---
title: '&lt;commonBehaviors&gt;'
ms.date: 03/30/2017
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
ms.openlocfilehash: 0a9fab68ce240fc37d27c42d9feff969b97f93a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350322"
---
# <a name="ltcommonbehaviorsgt"></a>&lt;commonBehaviors&gt;
La sezione `commonBehaviors` può essere definita solo nel file machine.config. e definisce due raccolte figlio denominate `endpointBehaviors` e `serviceBehaviors`.  Ogni raccolta definisce elementi di comportamento usati rispettivamente da tutti gli endpoint WCF e servizi del computer. I comportamenti definiti in `endpointBehaviors` vengono applicati solo ai client e i comportamenti definiti in `serviceBehaviors` vengono applicati solo ai servizi. Se un comportamento viene definito in entrambe le sezioni `commonBehaviors` e `behaviors`, la preferenza viene assegnata a quello nella sezione `behaviors`.
