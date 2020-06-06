---
title: Schema delle impostazioni di traccia e debug
ms.date: 03/30/2017
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
ms.openlocfilehash: 037d08b33e9aa6a64d236b36ebcf821b604b03df
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "69927124"
---
# <a name="trace-and-debug-settings-schema"></a>Schema delle impostazioni di traccia e debug
Le impostazioni di traccia e debug specificano i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.  
  
 La tabella seguente descrive la funzione di ogni elemento delle impostazioni di traccia e debug.  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-source.md)|Aggiunge un listener alla raccolta `Listeners` per un'origine di traccia.|  
|[\<add>](add-element-for-listeners-for-trace.md)|Aggiunge un listener alla raccolta `Listeners`.|  
|[\<add>](add-element-for-sharedlisteners.md)|Aggiunge un listener alla raccolta `sharedListeners`.|  
|[\<add>](add-element-for-switches.md)|Specifica il livello in cui viene impostata un'opzione di traccia.|  
|[\<assert>](assert-element.md)|Specifica se visualizzare una finestra di messaggio quando si chiama il metodo <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Specifica anche il nome del file in cui scrivere i messaggi.|  
|[\<clear>](clear-element-for-listeners-for-source.md)|Cancella la raccolta `Listeners` per un'origine di traccia.|  
|[\<clear>](clear-element-for-listeners-for-trace.md)|Cancella la raccolta `Listeners` per una traccia.|  
|[\<filter>](filter-element-for-add-for-listeners-for-source.md)|Aggiunge un filtro a un listener nella raccolta `Listeners` per un'origine di traccia.|  
|[\<filter>](filter-element-for-add-for-listeners-for-trace.md)|Aggiunge un filtro a un listener nella raccolta `Listeners` per la traccia.|  
|[\<filter>](filter-element-for-add-for-sharedlisteners.md)|Aggiunge un filtro a un listener nella raccolta `sharedListeners`.|  
|[\<listeners>](listeners-element-for-source.md)|Specifica i listener per la raccolta `Listeners` per un'origine di traccia.|  
|[\<listeners>](listeners-element-for-trace.md)|Specifica i listener per la raccolta `Listeners` per una traccia.|  
|[\<performanceCounters>](performancecounters-element.md)|Specifica le dimensioni della memoria globale condivisa dai contatori delle prestazioni.|  
|[\<remove>](remove-element-for-listeners-for-trace.md)|Rimuove un listener dalla raccolta `Listeners` per la traccia.|  
|[\<remove>](remove-element-for-listeners-for-source.md)|Rimuove un listener dalla raccolta `Listeners` per un'origine di traccia.|  
|[\<sharedListeners>](sharedlisteners-element.md)|Contiene i listener a cui può fare riferimento qualsiasi origine o elemento di traccia.|  
|[\<sources>](sources-element.md)|Contiene le origini di traccia che avviano i messaggi di traccia.|  
|[\<source>](source-element.md)|Specifica un'origine di traccia che avvia i messaggi di traccia.|  
|[\<switches>](switches-element.md)|Contiene le opzioni di traccia e il livello in cui vengono impostate le opzioni di traccia.|  
|[\<system.diagnostics>](system-diagnostics-element.md)|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
|[\<trace>](trace-element.md)|Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.|  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.Debug>
- [Schema del file di configurazione](../index.md)
