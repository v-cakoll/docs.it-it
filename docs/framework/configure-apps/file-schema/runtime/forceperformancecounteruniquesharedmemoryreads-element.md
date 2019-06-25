---
title: <forcePerformanceCounterUniqueSharedMemoryReads> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 00af9cf60d0bd2bac60950617b1315579d1a5a4d
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "67347343"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a>\<forcePerformanceCounterUniqueSharedMemoryReads > elemento
Specifica se PerfCounter.dll usa l'impostazione del Registro di sistema CategoryOptions in un'applicazione di .NET Framework versione 1.1 per determinare se caricare i dati del contatore delle prestazioni dalla memoria condivisa specifica della categoria o dalla memoria globale.  
  
 \<configuration>  
\<runtime>  
\<forcePerformanceCounterUniqueSharedMemoryReads>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Indica se PerfCounter. dll Usa l'impostazione del Registro di sistema CategoryOptions per determinare se caricare i dati dei contatori delle prestazioni di memoria condivisa specifica della categoria o della memoria globale.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`false`|PerfCounter non usa il CategoryOptions questa impostazione del registro è il valore predefinito.|  
|`true`|PerfCounter usare l'impostazione del Registro di sistema CategoryOptions.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Nelle versioni di .NET Framework precedenti a .NET Framework 4, la versione di PerfCounter. dll è stato caricato corrispondeva al runtime che è stato caricato nel processo. Se un computer dispone di .NET Framework versione 1.1 sia installato .NET Framework 2.0, un'applicazione .NET Framework 1.1 carica la versione di .NET Framework 1.1 di PerfCounter. dll. A partire da .NET Framework 4, la versione installata più recente di PerfCounter. dll viene caricata. Ciò significa che un'applicazione .NET Framework 1.1 caricherà la versione di .NET Framework 4 di PerfCounter se .NET Framework 4 è installato nel computer.  
  
 A partire da .NET Framework 4, quando si utilizzano contatori delle prestazioni, PerfCounter controlla la voce del Registro di sistema CategoryOptions per ogni provider determinare se è necessario leggere dalla memoria condivisa specifica della categoria o la memoria condivisa globale. Il .NET Framework 1.1 PerfCounter. dll non legge tale voce del Registro di sistema, perché non è conoscenza di memoria condivisa specifiche della categoria. legge sempre dalla memoria condivisa globale.  
  
 Per motivi di compatibilità di .NET Framework 4 PerfCounter. dll non verifica la voce del Registro di sistema CategoryOptions durante l'esecuzione in un'applicazione .NET Framework 1.1. Utilizza semplicemente memoria condivisa globale, esattamente come il .NET Framework 1.1 PerfCounter. dll. Si può però istruire il PerfCounter 4 di .NET Framework per verificare l'impostazione del Registro di sistema, consentendo la `<forcePerformanceCounterUniqueSharedMemoryReads>` elemento.  
  
> [!NOTE]
>  L'abilitazione di `<forcePerformanceCounterUniqueSharedMemoryReads>` elemento non garantisce che verrà utilizzata la memoria condivisa specifiche della categoria. Impostazione abilitata a `true` fa sì che solo fare riferimento l'impostazione del Registro di sistema CategoryOptions PerfCounter. dll. L'impostazione predefinita per CategoryOptions consiste nell'usare specifiche della categoria memoria condivisa. Tuttavia, è possibile modificare CategoryOptions per indicare che la memoria condivisa globale deve essere utilizzata.  
  
 La chiave del Registro di sistema che contiene l'impostazione CategoryOptions è HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\< categoryName\>\Performance. Per impostazione predefinita, CategoryOptions è impostato su 3, che indica di PerfCounter. dll da utilizzare memoria condivisa specifica della categoria. Se CategoryOptions è impostato su 0, PerfCounter utilizza memoria condivisa globale. I dati dell'istanza verranno riutilizzati solo se il nome dell'istanza da creare è identico all'istanza vengono riutilizzato. Tutte le versioni sarà in grado di scrivere in tale categoria. Se CategoryOptions è impostato su 1, viene utilizzata la memoria condivisa globale, ma i dati dell'istanza possono essere riutilizzati se il nome della categoria è uguale alla lunghezza della categoria verrà riutilizzata.  
  
 Le impostazioni di 0 e 1 possono causare perdite di memoria e il riempimento del memoria dei contatori delle prestazioni.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare che PerfCounter devono fare riferimento la voce del Registro di sistema CategoryOptions per determinare se deve utilizzare memoria condivisa specifica della categoria.  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
