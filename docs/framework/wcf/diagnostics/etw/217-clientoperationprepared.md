---
title: 217 - ClientOperationPrepared
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad207f04-b038-4f33-95e9-27a361df8ecd
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5062d2c2146dae8b22165cfbea0c6a78241d17b8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="217---clientoperationprepared"></a>217 - ClientOperationPrepared
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|217|  
|Parole chiave|Troubleshooting, ServiceModel|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Questo evento viene generato dai client prima che un'operazione venga inviata al servizio.  
  
## <a name="message"></a>Messaggio  
 Esecuzione dell'azione client '%1' associata al contratto '%2'. Il messaggio verrà inviato a '%3'.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Operazione|`xs:string`|Intestazione dell'azione SOAP del messaggio in uscita.|  
|Nome contratto|`xs:string`|Nome del contratto. Esempio: ICalculator.|  
|Destinazione|`xs:string`|Indirizzo dell'endpoint servizio a cui viene inviato il messaggio.|  
|HostReference|`xs:string`|Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web. Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'. Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.|  
|AppDomain|`xs:string`|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
