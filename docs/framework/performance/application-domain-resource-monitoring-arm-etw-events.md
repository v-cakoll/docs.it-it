---
title: Eventi ETW di monitoraggio delle risorse del dominio applicazione (ARM)
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0e4002ae248022a9e4380c79174109494b5e4ca
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046776"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a>Eventi ETW di monitoraggio delle risorse del dominio applicazione (ARM)
<a name="top"></a> Questi eventi forniscono informazioni di diagnostica dettagliate sullo stato di un dominio applicazione. È possibile usare questi eventi o la funzionalità di monitoraggio delle risorse del dominio applicazione (ARM) per ottenere le stesse informazioni.  
  
 Questa categoria include i seguenti eventi:  
  
- [Evento ThreadCreated](#threadcreated_event)  
  
- [Evento AppDomainMemAllocated](#appdomainmemallocated_event)  
  
- [Evento AppDomainMemSurvived](#appdomainmemsurvived_event)  
  
- [Evento ThreadAppDomainEnter](#threadappdomainenter_event)  
  
- [Evento ThreadTerminated](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a>Evento ThreadCreated  
 Questo evento viene generato anche nel provider di rundown come `ThreadDC` (sotto la parola chiave `AppDomainResourceManagementRundownKeyword` ). Questo è l'unico evento che viene generato nel provider di rundown in questa categoria.  
  
 La tabella seguente illustra la parola chiave e il livello Per altre informazioni, vedere [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).  
  
|Parola chiave per la generazione dell'evento|Level|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` (0x800)|Informativo (4)|  
|`ThreadingKeyword` (0x10000)|Informativo (4)|  
  
 La tabella seguente mostra le informazioni sull'evento.  
  
|event|ID evento|Generato quando|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|85|Un thread è stato creato per il dominio applicazione.|  
  
 La tabella seguente mostra i dati dell'evento.  
  
|Nome campo|Tipo di dati|Descrizione|  
|----------------|---------------|-----------------|  
|ThreadID|win:UInt64|ID del thread che è stato creato.|  
|AppDomainID|win:UInt64|Identificatore del dominio dell'applicazione per la quale l’attività thread viene segnalata.|  
|Flags|win:UInt32|Flag di creazione del thread.|  
|ManagedThreadIndex|win:UInt32|Indice gestito del thread che è stato creato.|  
|OSThreadID|win:UInt32|ID del sistema operativo che è stato creato.|  
|ClrInstanceID|win:UInt16|ID univoco per l'istanza di CLR o CoreCLR.|  
  
 [Torna all'inizio](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a>Evento AppDomainMemAllocated  
 La tabella seguente illustra la parola chiave e il livello  
  
|Parola chiave per la generazione dell'evento|Level|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` (0x800)|Informativo (4)|  
  
 La tabella seguente mostra le informazioni sull'evento.  
  
|event|ID evento|Generato quando|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|83|Ogni 4 MB di memoria (approssimativamente) viene allocato nel dominio dell'applicazione.|  
  
 La tabella seguente mostra i dati dell'evento.  
  
|Nome campo|Tipo di dati|DESCRIZIONE|  
|----------------|---------------|-----------------|  
|AppDomainID|win:UInt64|Identificatore del dominio dell'applicazione per la quale viene segnalato l’utilizzo della risorsa.|  
|Allocato|win:UInt64|Il numero totale di byte allocati in questo dominio applicazione, poiché è stato creato il dominio dell'applicazione (non viene sottratta la quantità di memoria liberata).|  
|ClrInstanceID|win:UInt16|ID univoco per l'istanza di CLR o CoreCLR.|  
  
 [Torna all'inizio](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a>Evento AppDomainMemSurvived  
 La tabella seguente illustra la parola chiave e il livello  
  
|Parola chiave per la generazione dell'evento|Level|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` (0x800)|Informativo (4)|  
  
 La tabella seguente mostra le informazioni sull'evento.  
  
|event|ID evento|Generato quando|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|84|Ogni operazione di Garbage Collection è stata terminata.|  
  
 La tabella seguente mostra i dati dell'evento.  
  
|Nome campo|Tipo di dati|Descrizione|  
|----------------|---------------|-----------------|  
|AppDomainID|win:UInt64|Identificatore del dominio per la quale viene segnalato l’utilizzo della risorsa.|  
|Survived|win:UInt64|Il numero di byte rimasti dall'ultima raccolta e a cui fa riferimento il dominio applicazione corrente. Questo numero è preciso e completo dopo una raccolta completa, ma può essere incompleto dopo una raccolta temporanea.|  
|ProcessSurvived|win:UInt64|I byte totali rimasti dall'ultima raccolta. Dopo una raccolta completa, questo numero rappresenta il numero di byte mantenuti attivi negli heap gestiti. Dopo una raccolta completa, questo numero rappresenta il numero di byte mantenuti attivi in generazioni temporanee.|  
|ClrInstanceID|win:UInt16|ID univoco per l'istanza di CLR o CoreCLR.|  
  
 [Torna all'inizio](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a>Evento ThreadAppDomainEnter  
 La tabella seguente illustra la parola chiave e il livello  
  
|Parola chiave per la generazione dell'evento|Level|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` (0x800)|Informativo (4)|  
|`ThreadingKeyword` (0x10000)|Informativo (4)|  
  
 La tabella seguente mostra le informazioni sull'evento.  
  
|event|ID evento|Generato quando|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|87|Un thread immette un dominio applicazione.|  
  
 La tabella seguente mostra i dati dell'evento.  
  
|Nome campo|Tipo di dati|Descrizione|  
|----------------|---------------|-----------------|  
|ThreadID|win:UInt64|L'identificatore del thread.|  
|AppDomainID|win:UInt64|L’identificatore di dominio applicazione.|  
|ClrInstanceID|win:UInt16|ID univoco per l'istanza di CLR o CoreCLR.|  
  
 [Torna all'inizio](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a>Evento ThreadTerminated  
 La tabella seguente illustra la parola chiave e il livello  
  
|Parola chiave per la generazione dell'evento|Level|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` (0x800)|Informativo (4)|  
|`ThreadingKeyword` (0x10000)|Informativo (4)|  
  
 La tabella seguente mostra le informazioni sull'evento.  
  
|event|ID evento|Generato quando|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|86|Termina un thread.|  
  
 La tabella seguente mostra i dati dell'evento:  
  
|Nome campo|Tipo di dati|Descrizione|  
|----------------|---------------|-----------------|  
|ThreadID|win:UInt64|L'identificatore del thread.|  
|AppDomainID|win:UInt64|L’identificatore di dominio applicazione.|  
|ClrInstanceID|win:UInt16|ID univoco per l'istanza di CLR o CoreCLR.|  
  
## <a name="see-also"></a>Vedere anche

- [Eventi ETW di CLR](clr-etw-events.md)
