---
title: 202 - ClientMessageInspectorBeforeSendInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b02ca82-8a55-45e3-b2e2-ddfe28a7269c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f6d737a7334098961cccb73a114be9be5bb71727
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="202---clientmessageinspectorbeforesendinvoked"></a>202 - ClientMessageInspectorBeforeSendInvoked
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|202|  
|Parole chiave|Troubleshooting, ServiceModel|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Questo evento viene generato dopo che il modello di servizi ha richiamato il metodo `BeforeSendRequest` su un controllo dei messaggi client.  
  
## <a name="message"></a>Messaggio  
 'BeforeSendRequest' richiamato dal dispatcher in un elemento ClientMessageInspector di tipo '%1'.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|TypeName|`xs:string`|Nome completo CLR del tipo di controllo richiamato.|  
|HostReference|`xs:string`|Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web. Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'. Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.|  
|AppDomain|`xs:string`|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
