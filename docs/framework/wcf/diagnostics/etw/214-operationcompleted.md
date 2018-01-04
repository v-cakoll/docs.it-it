---
title: 214 - OperationCompleted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6287eef-023f-4816-813c-1802c82366df
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 823207f4225252d94bd8fba450eb63edd00068ba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="214---operationcompleted"></a>214 - OperationCompleted
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|214|  
|Parole chiave|HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Questo evento viene generato quando l'elemento `OperationInvoker` predefinito del modello di servizi ha completato una chiamata a un metodo senza che quest'ultimo generasse un'eccezione.  
  
## <a name="message"></a>Messaggio  
 Chiamata al metodo '%1' da parte di OperationInvoker completata. Durata della chiamata al metodo: '%2' ms.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Nome metodo|`xs:string`|Nome CLR del metodo richiamato dall'elemento `OperationInvoker`.|  
|Durata|`xs:long`|Durata, in millisecondi, necessaria all'elemento `OperationInvoker` per richiamare il metodo.|  
|HostReference|`xs:string`|Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web. Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'. Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.|  
|AppDomain|`xs:string`|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
