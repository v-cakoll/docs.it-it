---
title: 1012 - StartExecuteActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6a3b03e8ac24bc1652b88b71e8c25862a07c194f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="1012---startexecuteactivityworkitem"></a>1012 - StartExecuteActivityWorkItem
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|1012|  
|Parole chiave|WFRuntime|  
|Livello|Dettagliato|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che viene avviata l'esecuzione di ExecuteActivityWorkItem.  
  
## <a name="message"></a>Messaggio  
 Avvio dell'esecuzione di ExecuteActivityWorkItem per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Attività|xs:string|Il nome del tipo di attività.|  
|DisplayName|xs:string|Nome visualizzato dell'attività.|  
|InstanceId|xs:string|L'ID dell'istanza dell'attività.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
