---
title: 1006 - WorkflowApplicationUnhandledException
ms.date: 03/30/2017
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
ms.openlocfilehash: 471f3ecea66ebbd07a09686ab536a84b25d46e6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924709"
---
# <a name="1006---workflowapplicationunhandledexception"></a>1006 - WorkflowApplicationUnhandledException
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|1006|  
|Parole chiave|WFRuntime|  
|Livello|Error|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che un'applicazione flusso di lavoro ha rilevato un'eccezione non gestita.  
  
## <a name="message"></a>Messaggio  
 WorkflowInstance con Id: '%1' ha rilevato un'eccezione non gestita.  Eccezione originata dall'attività '%2', DisplayName: '%3'.  Le seguenti azioni vengono intraprese: %4.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|`xs:string`|ID istanza del flusso di lavoro.|  
|Eccezione|`xs:string`|Dettagli dell'eccezione.|  
|AppDomain|`xs:string`|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
