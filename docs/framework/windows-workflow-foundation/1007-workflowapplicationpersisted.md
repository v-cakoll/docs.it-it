---
title: 1007 - WorkflowApplicationPersisted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f4ea4452-28e3-4e66-93c6-eb12ee29bcb1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0ddeb7cc60ec7b7976f8ba6b11ce3cd6a41d51a4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="1007---workflowapplicationpersisted"></a>1007 - WorkflowApplicationPersisted
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|1007|  
|Parole chiave|WFRuntime|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che un'applicazione flusso di lavoro è persistente.  
  
## <a name="message"></a>Messaggio  
 WorkflowApplication con ID: '%1' persistente.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|WorkflowApplicationId|`xs:string`|ID applicazione flusso di lavoro|  
|AppDomain|`xs:string`|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
