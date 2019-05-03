---
title: 205 - OperationInvoked
ms.date: 03/30/2017
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
ms.openlocfilehash: e95b6923d21307b2ef68d4a5369b3cee86540239
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781979"
---
# <a name="205---operationinvoked"></a>205 - OperationInvoked
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|205|  
|Parole chiave|Troubleshooting, ServiceModel|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Questo evento viene generato precedentemente alla chiamata a un metodo da parte dell'elemento `OperationInvoker` predefinito del modello di servizi.  
  
## <a name="message"></a>Messaggio  
 Metodo '%1' richiamato da OperationInvoker. Informazioni sul chiamante: '%2'.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Nome metodo|`xs:string`|Nome CLR del metodo richiamato dall'elemento `OperationInvoker`.|  
|Informazioni sul chiamante|`xs:string`|Indirizzo IP e numero di porta del client nel formato 'IndirizzoIP:NumeroPorta'. I due valori vengono recuperati dalla proprietà 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' del messaggio all'interno del contesto dell'operazione. Per le associazioni non TCP questo valore è `null`.|  
|HostReference|`xs:string`|Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web. Il formato viene definito come ' percorso virtuale dell'applicazione nome sito Web&#124;percorso virtuale del servizio&#124;ServiceName'. Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
