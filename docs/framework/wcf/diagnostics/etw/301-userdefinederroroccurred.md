---
title: 301 - UserDefinedErrorOccurred
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0285d1c-550f-4c14-9c36-a96e97f1c4e4
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b24d54930a29a24dab97ce403c2808fb74b8cbfe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="301---userdefinederroroccurred"></a>301 - UserDefinedErrorOccurred
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|301|  
|Parole chiave|Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring|  
|Livello|Errore|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Questo evento viene generato dal codice utente. Gli sviluppatori possono generare questo evento nel caso in cui si verifichi un errore definito dal cliente nel servizio. A tale scopo utilizzare le interfacce API <xref:System.Diagnostics.Eventing>. È inoltre disponibile un esempio WCF che esegue il wrapping dell'interfaccia API e illustra come generare correttamente questo evento.  
  
## <a name="message"></a>Messaggio  
 Nome:'%1', riferimento:'%2', payload:%3  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|nome|`xs:string`|Nome dell'evento definito dall'utente.|  
|HostReference|`xs:string`|Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web. Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'. Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.|  
|Payload|`xs:string`|Payload dell'evento definito dall'utente.|
