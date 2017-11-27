---
title: 1103 - WorkflowActivitySuspend
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b64e15c2-cb2c-4314-9074-ce2c6717232e
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a55cd953b294ca5e8a90f6ade666c55b51dc1e58
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1103---workflowactivitysuspend"></a>1103 - WorkflowActivitySuspend
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|1103|  
|Parole chiave|WFRuntime|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che un'attività del flusso di lavoro è stata sospesa.  
  
## <a name="message"></a>Messaggio  
 Attività end-to-end di WorkflowInstance con ID: '%1'  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|xs:string|ID dell'istanza del flusso di lavoro.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
