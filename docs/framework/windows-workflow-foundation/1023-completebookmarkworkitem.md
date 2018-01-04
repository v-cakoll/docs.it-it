---
title: 1023 - CompleteBookmarkWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc5dac57-b3eb-4826-b505-c6d269e4774d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6257cd9edcab7719bc52f785350d1b93e793c5b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="1023---completebookmarkworkitem"></a>1023 - CompleteBookmarkWorkItem
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|1023|  
|Parole chiave|WFRuntime|  
|Livello|Dettagliato|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che BookmarkWorkItem è completato.  
  
## <a name="message"></a>Messaggio  
 BookmarkWorkItem completato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'. BookmarkName: %4, BookmarkScope: %5.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Attività|xs:string|Il nome del tipo di attività.|  
|DisplayName|xs:string|Nome visualizzato dell'attività.|  
|InstanceId|xs:string|L'ID dell'istanza dell'attività.|  
|BookmarkName|xs:string|Nome del segnalibro.|  
|BookmarkScope|xs:string|Ambito del segnalibro.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
