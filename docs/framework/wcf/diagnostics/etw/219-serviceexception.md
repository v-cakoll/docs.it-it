---
title: 219 - ServiceException
ms.date: 03/30/2017
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
ms.openlocfilehash: eb4289c0346c9e1d9481347d69db8c5f007e4325
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781732"
---
# <a name="219---serviceexception"></a>219 - ServiceException
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|219|  
|Parole chiave|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel|  
|Livello|Error|  
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
|HostReference|`xs:string`|Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web. Il formato viene definito come ' percorso virtuale dell'applicazione nome sito Web&#124;percorso virtuale del servizio&#124;ServiceName'. Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
