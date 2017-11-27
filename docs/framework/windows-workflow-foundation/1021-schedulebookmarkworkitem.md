---
title: 1021 - ScheduleBookmarkWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3dc30100cb134740f51e6b2b38c00b2054d2ab0a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1021---schedulebookmarkworkitem"></a>1021 - ScheduleBookmarkWorkItem
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|1021|  
|Parole chiave|WFRuntime|  
|Livello|Dettagliato|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che un elemento BookmarkWorkItem è stato pianificato.  
  
## <a name="message"></a>Messaggio  
 BookmarkWorkItem pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.  BookmarkName: %4, BookmarkScope: %5.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Attività|xs:string|Il nome del tipo di attività.|  
|DisplayName|xs:string|Nome visualizzato dell'attività.|  
|InstanceId|xs:string|L'ID dell'istanza dell'attività.|  
|BookmarkName|xs:string|Nome del segnalibro.|  
|BookmarkScope|xs:string|Ambito del segnalibro.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
