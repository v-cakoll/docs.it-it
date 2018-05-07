---
title: 222 - OperationFailed
ms.date: 03/30/2017
ms.assetid: 6b530ded-8f20-4d78-8bfe-1875276df6ba
ms.openlocfilehash: c49aad0f93ce47b66306d75741267530dc6d3fe5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="222---operationfailed"></a>222 - OperationFailed
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|222|  
|Parole chiave|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel|  
|Livello|Avviso|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Questo evento viene generato quando l'elemento `OperationInvoker` predefinito del modello di servizi ha incontrato un'eccezione in fase di richiamo del metodo. Le eccezioni derivanti da `FaultException` impediscono la generazione di questo evento.  
  
## <a name="message"></a>Messaggio  
 Il metodo '%1' ha generato un'eccezione non gestita quando è stato richiamato da OperationInvoker. Durata della chiamata al metodo: '%2' ms.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Nome metodo|`xs:string`|Nome CLR del metodo richiamato dall'elemento `OperationInvoker`.|  
|Durata|`xs:long`|Durata, in millisecondi, necessaria all'elemento `OperationInvoker` per richiamare il metodo.|  
|HostReference|`xs:string`|Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web. Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso&#124;percorso virtuale servizio&#124;nomeservizio '. Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
