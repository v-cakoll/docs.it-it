---
title: Runnable Instances Detection Period
ms.date: 03/30/2017
ms.assetid: 4ea5c787-b638-47fd-bfc8-ede8c2898ce6
ms.openlocfilehash: 9652dd811f64e5324219b8aa0700ab8219edeeb0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937956"
---
# <a name="runnable-instances-detection-period"></a>Runnable Instances Detection Period
L'archivio di istanze del flusso di lavoro SQL esegue un'attività interna che attiva e rileva periodicamente istanze eseguibili o attivabili nel database di persistenza. Il **Runnable Instances Detection Period** proprietà di Store di istanza del flusso di lavoro di SQL specifica il periodo di tempo dopo il quale la Store di istanza del flusso di lavoro SQL esegue un'attività di rilevamento per rilevare qualsiasi flusso di lavoro eseguibile o attivabili istanze nel database di persistenza dopo il ciclo di rilevamento precedente.  
  
 L'impostazione di un intervallo più breve per questa proprietà riduce il tempo tra la scadenza di un timer associato a un'istanza del flusso di lavoro e la segnalazione dell'evento e il successivo caricamento dell'istanza. Tuttavia, aumenta anche il carico di elaborazione su un host e ciò può risultare non appropriato in scenari con timer durevoli e/o errori host. Il tipo della proprietà è TimeSpan e il valore della proprietà segue il formato: hh:mm:ss. Il valore minimo per questa proprietà è 00:00:01. Il valore predefinito della proprietà è 00:00:05.  
  
 Per altre informazioni vedere rilevamento e attivazione di istanze del flusso di lavoro eseguibili e attivabili [attivazione di istanze](instance-activation.md).
