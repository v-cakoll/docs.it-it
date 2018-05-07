---
title: 225 - TraceCorrelationKeys
ms.date: 03/30/2017
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
ms.openlocfilehash: 0bb54387dbd738a01225008edfc45ecb7297cd00
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="225---tracecorrelationkeys"></a>225 - TraceCorrelationKeys
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|225|  
|Parole chiave|Troubleshooting, ServiceModel|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Questo evento viene generato quando per un servizio flusso di lavoro viene usata la correlazione basata sul contenuto. Contiene le chiavi di correlazione applicate per correlare un messaggio a un'istanza.  
  
## <a name="message"></a>Messaggio  
 Chiave di correlazione '%1' calcolata usando i valori '%2' nell'ambito padre '%3'.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Chiave di istanza|`xs:GUID`|Chiave generata dai valori di correlazione.|  
|Valori|`xs:string`|Valori usati per calcolare la chiave dell'istanza di correlazione.|  
|Ambito padre|`xs:string`||  
|HostReference|`xs:string`|Per i servizi ospitati su Web questo campo identifica in modo univoco il servizio nella gerarchia Web. Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso&#124;percorso virtuale servizio&#124;nomeservizio '. Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
