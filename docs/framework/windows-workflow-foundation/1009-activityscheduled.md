---
title: 1009 - ActivityScheduled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4a0d8cc3d17ecd13d9312b42554ef5347cccf213
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="1009---activityscheduled"></a>1009 - ActivityScheduled
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|1009|  
|Parole chiave|WFRuntime|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che un'attività è pianificata per l'esecuzione.  
  
## <a name="message"></a>Messaggio  
 L'attività padre '%1', DisplayName: '%2', InstanceId: '%3' ha pianificato l'attività figlio '%4'', DisplayName: '%5', InstanceId: '%6'.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|ParentActivity|xs:string|Nome tipo dell'attività padre.|  
|ParentDisplayName|xs:string|Nome visualizzato dell'attività padre.|  
|ParentInstanceId|xs:string|ID dell'istanza dell'attività padre.|  
|ChildActivity|xs:string|Nome del tipo dell'attività figlio pianificata.|  
|ChildDisplayName|xs:string|Nome visualizzato dell'attività figlio pianificata.|  
|ChildInstanceId|xs:string|ID istanza dell'attività figlio pianificata.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
