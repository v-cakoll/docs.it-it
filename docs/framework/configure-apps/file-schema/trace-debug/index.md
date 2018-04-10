---
title: Schema delle impostazioni di traccia e debug
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracing [.NET Framework], trace and debug settings schema
- configuration schema [.NET Framework], trace and debug settings
- configuration settings [.NET Framework], tracing
- schema configuration settings
- configuration settings [.NET Framework], debugging
- trace listeners, trace and debug settings schema
- configuration sections [.NET Framework]
- elements [.NET Framework], trace and debug settings
ms.assetid: 277ca5f6-e1c4-41b6-a47f-3a67ce5b94ac
caps.latest.revision: 14
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: e6d9e5ca97e4d5940dd9de3f3ffbd4db4183196c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="trace-and-debug-settings-schema"></a>Schema delle impostazioni di traccia e debug
Le impostazioni di traccia e debug specificano i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.  
  
 La tabella seguente descrive la funzione di ogni elemento delle impostazioni di traccia e debug.  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-source.md)|Aggiunge un listener alla raccolta `Listeners` per un'origine di traccia.|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|Aggiunge un listener alla raccolta `Listeners`.|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-sharedlisteners.md)|Aggiunge un listener alla raccolta `sharedListeners`.|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|Specifica il livello in cui viene impostata un'opzione di traccia.|  
|[\<assert>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|Specifica se visualizzare una finestra di messaggio quando si chiama il metodo <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Specifica anche il nome del file in cui scrivere i messaggi.|  
|[\<clear>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)|Cancella la raccolta `Listeners` per un'origine di traccia.|  
|[\<clear>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-trace.md)|Cancella la raccolta `Listeners` per una traccia.|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-source.md)|Aggiunge un filtro a un listener nella raccolta `Listeners` per un'origine di traccia.|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|Aggiunge un filtro a un listener nella raccolta `Listeners` per la traccia.|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|Aggiunge un filtro a un listener nella raccolta `sharedListeners`.|  
|[\<listeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|Specifica i listener per la raccolta `Listeners` per un'origine di traccia.|  
|[\<listeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|Specifica i listener per la raccolta `Listeners` per una traccia.|  
|[\<performanceCounters>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|Specifica le dimensioni della memoria globale condivisa dai contatori delle prestazioni.|  
|[\<remove>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)|Rimuove un listener dalla raccolta `Listeners` per la traccia.|  
|[\<remove>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-source.md)|Rimuove un listener dalla raccolta `Listeners` per un'origine di traccia.|  
|[\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|Contiene i listener a cui può fare riferimento qualsiasi origine o elemento di traccia.|  
|[\<sources>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|Contiene le origini di traccia che avviano i messaggi di traccia.|  
|[\<source>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)|Specifica un'origine di traccia che avvia i messaggi di traccia.|  
|[\<switches>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|Contiene le opzioni di traccia e il livello in cui vengono impostate le opzioni di traccia.|  
|[\<system.diagnostics>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/system-diagnostics-element.md)|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
|[\<trace>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.Debug>  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
