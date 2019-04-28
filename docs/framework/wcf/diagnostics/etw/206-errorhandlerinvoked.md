---
title: 206 - ErrorHandlerInvoked
ms.date: 03/30/2017
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
ms.openlocfilehash: 40a92d77c57728249569a854eab8767ff371bca2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781927"
---
# <a name="206---errorhandlerinvoked"></a>206 - ErrorHandlerInvoked
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|206|  
|Parole chiave|Troubleshooting, ServiceModel|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Questo evento viene generato dopo che un `ErrorHandler` ha avuto la possibilità di gestire un'eccezione verificatasi in un'operazione del servizio.  
  
## <a name="message"></a>Messaggio  
 ErrorHandler di tipo '%1' con un'eccezione di tipo '%3' richiamato dal Dispatcher. ErrorHandled == '%2'.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|TypeName|`xs:string`|Nome completo CLR del tipo dell'elemento `ErrorHandler` richiamato.|  
|Handled|`xs:unsignedByte`|`true` se l'errore è stato gestito. In caso contrario, `false`.|  
|ExceptionTypeName|`xs:string`|Nome completo CLR dell'eccezione gestita.|  
|HostReference|`xs:string`|Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web. Il formato viene definito come ' percorso virtuale dell'applicazione nome sito Web&#124;percorso virtuale del servizio&#124;ServiceName'. Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
