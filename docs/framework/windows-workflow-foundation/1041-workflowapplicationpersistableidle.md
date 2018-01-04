---
title: 1041 - WorkflowApplicationPersistableIdle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1efc32ed0304d5b0d222054e5c65abe279ef93ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="1041---workflowapplicationpersistableidle"></a>1041 - WorkflowApplicationPersistableIdle
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|1041|  
|Parole chiave|WFRuntime|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che un'applicazione flusso di lavoro è inattiva e persistente. L'applicazione flusso di lavoro verrà resa inattiva o persistente.  
  
## <a name="message"></a>Messaggio  
 Workflowapplication con Id: '%1' è inattiva e persistente.  Verrà effettuata l'azione seguente: %2.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|WorkflowApplicationId|xs:string|ID applicazione flusso di lavoro|  
|ActionTaken|xs:string|L'azione che verrà intrapresa sull'applicazione flusso di lavoro.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
