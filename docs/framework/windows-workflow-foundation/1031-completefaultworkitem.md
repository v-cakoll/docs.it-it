---
title: 1031 - CompleteFaultWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a87ecb0a50437d83dd3c80d213553c8ac2143968
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="1031---completefaultworkitem"></a>1031 - CompleteFaultWorkItem
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|1031|  
|Parole chiave|WFRuntime|  
|Livello|Dettagliato|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che FaultWorkItem è completato.  
  
## <a name="message"></a>Messaggio  
 FaultWorkItem completato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'. Eccezione propagata dall'attività '%4', DisplayName: '%5', InstanceId: '%6'.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|FaultActivity|xs:string|Il nome del tipo di attività fault.|  
|FaultActivityDisplayName|xs:string|Nome visualizzato dell'attività fault.|  
|FaultActivityInstanceId|xs:string|ID dell'istanza dell'attività fault.|  
|ExceptionActivity|xs:string|Il nome del tipo di attività che ha generato l'eccezione.|  
|ExceptionActivityDisplayName|xs:string|Il nome visualizzato dell'attività che ha generato l'eccezione.|  
|ExceptionActivityInstanceId|xs:string|ID dell'istanza dell'attività che ha generato l'eccezione.|  
|Eccezione|xs:string|Dettagli dell'eccezione.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
