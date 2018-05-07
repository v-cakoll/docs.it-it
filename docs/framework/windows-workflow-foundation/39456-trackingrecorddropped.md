---
title: 39456 - TrackingRecordDropped
ms.date: 03/30/2017
ms.assetid: da13d5bc-1736-47a4-b3fd-064ca8040326
ms.openlocfilehash: f117c7759bab1759a7d614db275de88f8b37c331
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="39456---trackingrecorddropped"></a>39456 - TrackingRecordDropped
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|39456|  
|Parole chiave|WFTracking|  
|Livello|Avviso|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che un record di rilevamento è stato eliminato perché le dimensioni superano il massimo consentito dal provider della sessione ETW.  
  
## <a name="message"></a>Messaggio  
 La dimensione del record di rilevamento %1 supera il valore massimo consentito dalla sessione ETW per il provider %2  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Eccezione|xs:string|Dettagli dell'eccezione.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
