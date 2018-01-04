---
title: 218 - ClientOperationCompleted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b069bced-7bb2-4e01-8227-e5dbda17af09
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 974fde79d8b24c17928fa4ff38bb9d35d6b5a815
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="218---clientoperationcompleted"></a>218 - ClientOperationCompleted
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|218|  
|Parole chiave|Troubleshooting, ServiceModel|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Questo evento viene generato dai client al termine di un'operazione. Per le operazioni unidirezionali, si tratta del momento successivo all'invio di un messaggio. Per le operazioni request-response, si tratta del momento successivo alla ricezione della risposta.  
  
## <a name="message"></a>Messaggio  
 L'azione client '%1' associata al contratto '%2' è completa. Il messaggio è stato inviato a '%3'.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Operazione|xs:string|Intestazione dell'azione SOAP del messaggio in uscita.|  
|Nome contratto|`xs:string`|Nome del contratto. Esempio: ICalculator.|  
|Destinazione|`xs:string`|Indirizzo dell'endpoint servizio a cui è stato inviato il messaggio.|  
|HostReference|`xs:string`|Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web. Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'. Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.|  
|AppDomain|`xs:string`|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
