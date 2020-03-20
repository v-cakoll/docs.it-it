---
title: <forcePerformanceCounterUniqueSharedMemoryReads> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
ms.openlocfilehash: 742b444c445ba67d6977b622e615a6a8f591826e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154140"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a>\<forcePerformanceCounterUniqueSharedMemoryReads> elemento
Specifica se PerfCounter.dll usa l'impostazione del Registro di sistema CategoryOptions in un'applicazione di .NET Framework versione 1.1 per determinare se caricare i dati del contatore delle prestazioni dalla memoria condivisa specifica della categoria o dalla memoria globale.  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>di runtime**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<forcePerformanceCounterUniqueSharedMemoryReads>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Indica se PerfCounter.dll utilizza l'impostazione del Registro di sistema CategoryOptions per determinare se caricare i dati dei contatori delle prestazioni dalla memoria condivisa specifica della categoria o dalla memoria globale.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|valore|Descrizione|  
|-----------|-----------------|  
|`false`|PerfCounter.dll non utilizza l'impostazione del Registro di sistema CategoryOptions Questa è l'impostazione predefinita.|  
|`true`|PerfCounter.dll utilizza l'impostazione del Registro di sistema CategoryOptions.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Osservazioni  
 Nelle versioni di .NET Framework precedenti a .NET Framework 4, la versione di PerfCounter.dll caricata corrispondeva al runtime caricato nel processo. Se in un computer è stato installato sia .NET Framework versione 1.1 che .NET Framework 2.0, un'applicazione .NET Framework 1.1 caricherebbe la versione .NET Framework 1.1 di PerfCounter.dll. A partire da .NET Framework 4. Ciò significa che un'applicazione .NET Framework 1.1 caricherà la versione .NET Framework 4 di PerfCounter.dll se .NET Framework 4 è installato nel computer.  
  
 A partire da .NET Framework 4.NET Framework 4, quando si utilizzano i contatori delle prestazioni, PerfCounter.dll controlla la voce del Registro di sistema CategoryOptions per ogni provider per determinare se deve leggere dalla memoria condivisa specifica della categoria o dalla memoria condivisa globale. .NET Framework 1.1 PerfCounter.dll non legge tale voce del Registro di sistema, perché non è a conoscenza della memoria condivisa specifica della categoria; legge sempre dalla memoria condivisa globale.  
  
 Per garantire la compatibilità con le versioni precedenti, .NET Framework 4 PerfCounter.dll non controlla la voce del Registro di sistema CategoryOptions durante l'esecuzione in un'applicazione .NET Framework 1.1. Utilizza semplicemente la memoria condivisa globale, proprio come il PerfCounter.dll di .NET Framework 1.1. Tuttavia, è possibile indicare a.NET Framework 4 PerfCounter.dll `<forcePerformanceCounterUniqueSharedMemoryReads>` per controllare l'impostazione del Registro di sistema attivando l'elemento.  
  
> [!NOTE]
> L'abilitazione dell'elemento `<forcePerformanceCounterUniqueSharedMemoryReads>` non garantisce l'utilizzo della memoria condivisa specifica della categoria. L'impostazione abilitata per `true` fare in modo che PerfCounter.dll faccia riferimento all'impostazione del Registro di sistema CategoryOptions. L'impostazione predefinita per CategoryOptions consiste nell'utilizzare la memoria condivisa specifica della categoria; Tuttavia, è possibile modificare CategoryOptions per indicare che deve essere utilizzata la memoria condivisa globale.  
  
 La chiave del Registro di sistema che contiene l'impostazione CategoryOptions è\\<\>HKEY_LOCAL_MACHINE . Per impostazione predefinita, CategoryOptions è impostato su 3, che indica a PerfCounter.dll di utilizzare la memoria condivisa specifica della categoria. Se CategoryOptions è impostato su 0, PerfCounter.dll utilizza la memoria condivisa globale. I dati dell'istanza verranno riutilizzati solo se il nome dell'istanza da creare è identico a quello dell'istanza da riutilizzare. Tutte le versioni saranno in grado di scrivere nella categoria. Se CategoryOptions è impostato su 1, viene utilizzata la memoria condivisa globale, ma i dati dell'istanza possono essere riutilizzati se il nome della categoria ha la stessa lunghezza della categoria riutilizzata.  
  
 Le impostazioni 0 e 1 possono causare perdite di memoria e il riempimento della memoria del contatore delle prestazioni.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare che PerfCounter.dll deve fare riferimento alla voce del Registro di sistema CategoryOptions per determinare se deve utilizzare memoria condivisa specifica della categoria.  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema del file di configurazione](../index.md)
