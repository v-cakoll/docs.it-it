---
title: 1022 - StartBookmarkWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4415fbdb-0329-4019-803f-aea66e75f3da
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cdb6af10c45e7a93e9a68e6150e5d239002cce04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="1022---startbookmarkworkitem"></a>1022 - StartBookmarkWorkItem
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|1022|  
|Parole chiave|WFRuntime|  
|Livello|Dettagliato|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che viene avviata l'esecuzione di BookmarkWorkItem.  
  
## <a name="message"></a>Messaggio  
 Avvio dell'esecuzione di BookmarkWorkItem per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.  BookmarkName: %4, BookmarkScope: %5.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Attività|xs:string|Il nome del tipo di attività.|  
|DisplayName|xs:string|Nome visualizzato dell'attività.|  
|InstanceId|xs:string|L'ID dell'istanza dell'attività.|  
|BookmarkName|xs:string|Nome del segnalibro.|  
|BookmarkScope|xs:string|Ambito del segnalibro.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
