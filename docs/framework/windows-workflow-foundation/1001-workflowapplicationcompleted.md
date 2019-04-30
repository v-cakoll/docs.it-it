---
title: 1001 - WorkflowApplicationCompleted
ms.date: 03/30/2017
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
ms.openlocfilehash: 430174b96a499fff7e0156327bb15e066ce2ca36
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008642"
---
# <a name="1001---workflowapplicationcompleted"></a>1001 - WorkflowApplicationCompleted
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|1001|  
|Parole chiave|WFRuntime|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che un'applicazione flusso di lavoro è stata completata nello stato Closed.  
  
## <a name="message"></a>Messaggio  
 WorkflowInstance con ID: '%1' completata nello stato Closed.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|`xs:string`|ID istanza del flusso di lavoro.|  
|AppDomain|`xs:string`|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
