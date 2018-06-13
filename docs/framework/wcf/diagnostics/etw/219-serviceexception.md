---
title: 219 - ServiceException
ms.date: 03/30/2017
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
ms.openlocfilehash: eb4289c0346c9e1d9481347d69db8c5f007e4325
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460515"
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
|HostReference|`xs:string`|Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web. Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso&#124;percorso virtuale servizio&#124;nomeservizio '. Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
