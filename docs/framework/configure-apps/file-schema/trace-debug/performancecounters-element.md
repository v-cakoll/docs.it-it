---
title: <performanceCounters> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <performanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
ms.openlocfilehash: f52fdb2d5b0b7911de63f96663e70735d2f2496c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "71697149"
---
# <a name="performancecounters-element"></a>\<performanceCounters> Elemento

Specifica le dimensioni della memoria globale condivisa dai contatori delle prestazioni.

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<performanceCounters>**  

## <a name="syntax"></a>Sintassi

```xml
<performanceCounters filemappingsize="524288" />
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

|Attributo|Descrizione|
|---------------|-----------------|
|FileMappingSize|Attributo obbligatorio.<br /><br /> Specifica la dimensione, in byte, della memoria globale condivisa dai contatori delle prestazioni. Il valore predefinito è 524288.|

### <a name="child-elements"></a>Elementi figlio

No.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`Configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`system.diagnostics`|Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.|

## <a name="remarks"></a>Commenti

I contatori delle prestazioni utilizzano un file mappato alla memoria o una memoria condivisa per pubblicare i dati sulle prestazioni.  Le dimensioni della memoria condivisa determinano il numero di istanze che possono essere usate contemporaneamente.  Esistono due tipi di memoria condivisa: memoria condivisa globale e memoria condivisa separata.  La memoria condivisa globale viene utilizzata da tutte le categorie di contatori delle prestazioni installate con le versioni .NET Framework 1,0 o 1,1.  Le categorie di contatori delle prestazioni installate con la versione di .NET Framework 2,0 usano una memoria condivisa separata, con ogni categoria di contatori delle prestazioni con memoria propria.

Le dimensioni della memoria condivisa globale possono essere impostate solo con un file di configurazione.  Le dimensioni predefinite sono pari a 524.288 addii, le cui dimensioni massime sono di 33.554.432 byte e la dimensione minima è 32.768 byte.  Poiché la memoria condivisa globale è condivisa da tutti i processi e le categorie, il primo autore specifica le dimensioni.  Se si definiscono le dimensioni nel file di configurazione dell'applicazione, tale dimensione viene utilizzata solo se l'applicazione è la prima applicazione che provoca l'esecuzione dei contatori delle prestazioni.  Il percorso corretto per specificare il `filemappingsize` valore è quindi il file Machine. config.  La memoria nella memoria condivisa globale non può essere rilasciata dai singoli contatori delle prestazioni, quindi la memoria condivisa globale viene esaurita se viene creato un numero elevato di istanze del contatore delle prestazioni con nomi diversi.

Per la dimensione della memoria condivisa separata, viene fatto riferimento prima del valore DWORD FileMappingSize nella chiave del registro di sistema HKEY_LOCAL_MACHINE \SYSTEM\CurrentControlSet\Services \\ *\<category name>* \Performance, seguito dal valore specificato per la memoria condivisa globale nel file di configurazione. Se il valore FileMappingSize non esiste, le dimensioni separate della memoria condivisa vengono impostate su un quarto (1/4) nell'impostazione globale nel file di configurazione.

## <a name="see-also"></a>Vedere anche

- <xref:System.Diagnostics.PerformanceCounter>
- <xref:System.Diagnostics.PerformanceCounterCategory>
- <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>
- <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
