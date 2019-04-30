---
title: 1103 - WorkflowActivitySuspend
ms.date: 03/30/2017
ms.assetid: b64e15c2-cb2c-4314-9074-ce2c6717232e
ms.openlocfilehash: 4311bd8dc1c5e2c43bf21b411a4c52a7bfc7b230
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052781"
---
# <a name="1103---workflowactivitysuspend"></a>1103 - WorkflowActivitySuspend
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|1103|  
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
