---
title: 210 - MessageThrottleExceeded
ms.date: 03/30/2017
ms.assetid: 24ca08ea-c11c-4753-946e-98aa820f8711
ms.openlocfilehash: 7ba5948b36642085ef44661b3d580e7f1c4102cb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781882"
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
 Questo evento viene generato quando viene superata una delle tre velocità del servizio principali. L'evento viene generato solo quando il limite di velocità viene superato in fase iniziale. Ad esempio, se il limite di velocità per le chiamate simultanee è 10, 11 simultaneo risultati delle chiamate un `MessageThrottleExceeded` evento. La chiamata 12th non comporta un altro evento. Un'attività che si aggira intorno al limite non comporta inoltre un altro evento, per evitare un flusso di eventi problematico. In questo esempio, se due chiamate vengono completate, saranno presenti 9 chiamate simultanee. Se in seguito entrano altre due chiamate, il valore corrente sarà nuovamente 11. Questa situazione non comporta un altro evento. Se il valore corrente corrisponde al 70% del limite di velocità, viene generato un evento diverso che indica che l'attività è rallentata. Un'attività futura che supera il limite comporta un altro evento `MessageThrottleExceeded` generato. In questo esempio, se la quantità di chiamate simultanee corrisponde a 7 e quindi nuovamente a 11, viene generato un altro evento `MessageThrottleExceeded`.  
  
## <a name="message"></a>Messaggio  
 È stato raggiunto il limite di velocità '%1' di '%2'.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Nome velocità|`xs:string`|Nome della velocità superata: `MaxConcurrentCalls`, `MaxConcurrentInstances` o `MaxConcurrentSessions`,|  
|Limit|`xs:long`|Limite attualmente configurato della velocità.|  
|HostReference|`xs:string`|Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web. Il formato viene definito come ' percorso virtuale dell'applicazione nome sito Web&#124;percorso virtuale del servizio&#124;ServiceName'. Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
