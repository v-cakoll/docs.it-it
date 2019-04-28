---
title: 224 - MessageThrottleAtSeventyPercent
ms.date: 03/30/2017
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
ms.openlocfilehash: f70dc235e037b4f490a25866940fe2bccceae2a1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916305"
---
# <a name="224---messagethrottleatseventypercent"></a>224 - MessageThrottleAtSeventyPercent
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|224|  
|Parole chiave|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel|  
|Livello|Avviso|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Se viene superata una delle velocità del servizio principali, viene generato l'evento `MessageThrottleExceeded`. Se il picco dell'attività rallenta e il valore corrente della velocità è pari al 70% del limite corrente, viene generato l'evento. Questo evento viene generato solo una volta, in quanto l'attività sta rallentando. Se il valore corrente si aggira attorno al limite del 70% (ad esempio, 70, 69, 70, 71, 70, 69), solo alla prima occorrenza di 70% verrà generato un evento. Una volta generato l'evento, le future occorrenze di superamento del limite della velocità genereranno un evento `MessageThrottleExceeded`.  
  
## <a name="message"></a>Messaggio  
 Il limite di velocità '%1' di '%2' è al 70%.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Nome velocità|`xs:string`|Nome della velocità superata: `MaxConcurrentCalls`, `MaxConcurrentInstances` o `MaxConcurrentSessions`,|  
|Limit|`xs:long`|Limite attualmente configurato della velocità.|  
|HostReference|`xs:string`|Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web. Il formato viene definito come ' percorso virtuale dell'applicazione nome sito Web&#124;percorso virtuale del servizio&#124;ServiceName'. Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
