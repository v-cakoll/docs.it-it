---
title: 210 - MessageThrottleExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24ca08ea-c11c-4753-946e-98aa820f8711
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 299cc11dc4f6794b65761ad7da71bcf062c318db
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="210---messagethrottleexceeded"></a>210 - MessageThrottleExceeded
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|210|  
|Parole chiave|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel|  
|Livello|Avviso|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Questo evento viene generato quando viene superata una delle tre velocità del servizio principali. L'evento viene generato solo quando il limite di velocità viene superato in fase iniziale. Se ad esempio il limite di velocità per le chiamate simultanee è 10, l'11ª chiamata simultanea comporta un evento `MessageThrottleExceeded`. La 12ª chiamata non comporta un altro evento. Un'attività che si aggira intorno al limite non comporta inoltre un altro evento, per evitare un flusso di eventi problematico. In questo esempio, se due chiamate vengono completate, saranno presenti 9 chiamate simultanee. Se in seguito entrano altre due chiamate, il valore corrente sarà nuovamente 11. Questa situazione non comporta un altro evento. Se il valore corrente corrisponde al 70% del limite di velocità, viene generato un evento diverso che indica che l'attività è rallentata. Un'attività futura che supera il limite comporta un altro evento `MessageThrottleExceeded` generato. In questo esempio, se la quantità di chiamate simultanee corrisponde a 7 e quindi nuovamente a 11, viene generato un altro evento `MessageThrottleExceeded`.  
  
## <a name="message"></a>Messaggio  
 È stato raggiunto il limite di velocità '%1' di '%2'.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Nome velocità|`xs:string`|Nome della velocità superata: `MaxConcurrentCalls`, `MaxConcurrentInstances` o `MaxConcurrentSessions`,|  
|Limit|`xs:long`|Limite attualmente configurato della velocità.|  
|HostReference|`xs:string`|Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web. Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'. Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.|  
|AppDomain|`xs:string`|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
