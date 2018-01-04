---
title: 219 - ServiceException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fceff5c748076c75c942f515e2621edff5106f4e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="219---serviceexception"></a>219 - ServiceException
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|219|  
|Parole chiave|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel|  
|Livello|Errore|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Questo evento viene generato quando un servizio WCF incontra un'eccezione non gestita. Include eccezioni non gestite durante l'attivazione, durante l'elaborazione dei messaggi e nel codice utente.  
  
## <a name="message"></a>Messaggio  
 Riscontrata un'eccezione non gestita di tipo '%2' durante l'elaborazione del messaggio. ToString completo dell'eccezione: %1.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|ExceptionToString|`xs:string`|Risultato della chiamata di `ToString`() all'eccezione CLR.|  
|ExceptionTypeName|`xs:string`|Nome completo CLR del tipo di eccezione.|  
|HostReference|`xs:string`|Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web. Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'. Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.|  
|AppDomain|`xs:string`|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
