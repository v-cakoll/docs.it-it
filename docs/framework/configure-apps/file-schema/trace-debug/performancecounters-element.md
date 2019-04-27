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
ms.openlocfilehash: 6144bcbda69b2ba799e87c3e7fa2118fbe4d9bf6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673741"
---
# <a name="performancecounters-element"></a>\<performanceCounters > elemento

Specifica le dimensioni della memoria globale condivisa dai contatori delle prestazioni.

 \<configuration>\
\<system.diagnostics>\
\<performanceCounters>

## <a name="syntax"></a>Sintassi

```xml
<performanceCounters filemappingsize="524288" />
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

|Attributo|Descrizione|
|---------------|-----------------|
|filemappingsize|Attributo obbligatorio.<br /><br /> Specifica le dimensioni, in byte, della memoria globale condivisa dai contatori delle prestazioni. Il valore predefinito è 524288.|

### <a name="child-elements"></a>Elementi figlio

Nessuno.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`Configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`system.diagnostics`|Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.|

## <a name="remarks"></a>Note

I contatori delle prestazioni utilizzano un file mappato alla memoria o della memoria condivisa, per pubblicare i dati sulle prestazioni.  Le dimensioni della memoria condivisa determinano il numero di istanze può essere utilizzato in una sola volta.  Esistono due tipi di memoria condivisa: memoria condivisa globale e della memoria condivisa separata.  La memoria condivisa globale viene usata da tutte le categorie di contatori delle prestazioni installate con le versioni di .NET Framework 1.0 o 1.1.  Categorie di contatori delle prestazioni installate con .NET Framework versione 2.0 usano memoria condivisa separata, con ogni categoria di contatori delle prestazioni disponga della propria memoria.

Le dimensioni della memoria condivisa globale possono essere impostate solo con un file di configurazione.  Il valore predefinito è 524.288, la dimensione massima è 33.554.432 byte e la dimensione minima è 32.768 byte.  Poiché la memoria condivisa globale è condiviso da tutti i processi e le categorie, l'autore prima specifica le dimensioni.  Se si definiscono le dimensioni nel file di configurazione dell'applicazione, che la dimensione viene usata solo se l'applicazione è la prima applicazione che fa sì che i contatori delle prestazioni per l'esecuzione.  Pertanto la posizione corretta per specificare il `filemappingsize` valore è il file Machine. config.  Impossibile rilasciare memoria nella memoria globale condivisa dai contatori delle prestazioni singoli, pertanto, alla fine viene esaurita la memoria globale condivisa se viene creato un numero elevato di istanze del contatore delle prestazioni con nomi diversi.

Per le dimensioni della memoria condivisa separata, il valore della chiave DWORD FileMappingSize nel Registro di sistema chiave HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<il nome di categoria >* \Performance viene fatto riferimento in primo luogo, seguito dal valore specificato per la memoria condivisa globale nel file di configurazione. Se il valore FileMappingSize non esiste, quindi le dimensioni di memoria condivisa separata sono impostata su un quarto (1 e 4) l'impostazione globale nel file di configurazione.

## <a name="see-also"></a>Vedere anche

- <xref:System.Diagnostics.PerformanceCounter>
- <xref:System.Diagnostics.PerformanceCounterCategory>
- <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>
- <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
