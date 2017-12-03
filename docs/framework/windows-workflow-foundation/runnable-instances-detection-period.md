---
title: Runnable Instances Detection Period
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ea5c787-b638-47fd-bfc8-ede8c2898ce6
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 18b016cdf51ec95ab8457ded2949b980fc66fad0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="runnable-instances-detection-period"></a>Runnable Instances Detection Period
L'archivio di istanze del flusso di lavoro SQL esegue un'attività interna che attiva e rileva periodicamente istanze eseguibili o attivabili nel database di persistenza. Il **Runnable Instances Detection Period** proprietà dell'archivio di istanze del flusso di lavoro SQL specifica il periodo di tempo trascorso il quale l'archivio di istanze del flusso di lavoro SQL esegue un'attività di rilevamento per rilevare qualsiasi flusso di lavoro eseguibile o attivabili istanze nel database di persistenza dopo il ciclo di rilevamento precedente.  
  
 L'impostazione di un intervallo più breve per questa proprietà riduce il tempo tra la scadenza di un timer associato a un'istanza del flusso di lavoro e la segnalazione dell'evento e il successivo caricamento dell'istanza. Tuttavia, aumenta anche il carico di elaborazione su un host e ciò può risultare non appropriato in scenari con timer durevoli e/o errori host. Il tipo della proprietà è TimeSpan e il valore della proprietà segue il formato: hh:mm:ss. Il valore minimo per questa proprietà è 00:00:01. Il valore predefinito della proprietà è 00:00:05.  
  
 Per ulteriori informazioni vedere rilevamento e attivazione di istanze del flusso di lavoro eseguibili e attivabile, [attivazione di istanze](../../../docs/framework/windows-workflow-foundation/instance-activation.md).
