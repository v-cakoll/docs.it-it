---
title: Impostazioni di configurazione del Garbage Collector
description: Informazioni sulle impostazioni di runtime per la configurazione del modo in cui il Garbage Collector gestisce la memoria per le app .NET Core.Learn about run-time settings for configuring how the garbage collector manages memory for .NET Core apps.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: ec575bdd17c8a7c290673b7085074bbba94cedef
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102866"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a>Opzioni di configurazione in fase di esecuzione per la procedura di Garbage CollectionRun-time configuration options for garbage collection

Questa pagina contiene informazioni sulle impostazioni del Garbage Collector (GC) che possono essere modificate in fase di esecuzione. Se stai cercando di ottenere prestazioni di picco di un'app in esecuzione, prendi in considerazione l'uso di queste impostazioni. Tuttavia, le impostazioni predefinite forniscono prestazioni ottimali per la maggior parte delle applicazioni in situazioni tipiche.

Le impostazioni sono organizzate in gruppi in questa pagina. Le impostazioni all'interno di ogni gruppo sono comunemente utilizzate in combinazione tra loro per ottenere un risultato specifico.

> [!NOTE]
>
> - Queste impostazioni possono anche essere modificate dinamicamente dall'app mentre è in esecuzione, pertanto qualsiasi impostazione di runtime impostata può essere sostituita.
> - Alcune impostazioni, ad esempio il livello di [latenza](../../standard/garbage-collection/latency.md), vengono in genere impostate solo tramite l'API in fase di progettazione. Tali impostazioni vengono omesse da questa pagina.
> - Per i valori numerici, utilizzare la notazione decimale per le impostazioni nel file *runtimeconfig.json* e la notazione esadecimale per le impostazioni delle variabili di ambiente. Per i valori esadecimali, è possibile specificarli con o senza il prefisso "0x".

## <a name="flavors-of-garbage-collection"></a>Sapori di garbage collection

I due tipi principali di garbage collection sono workstation GC e server GC. Per ulteriori informazioni sulle differenze tra i due, vedere [Garbage Collection per workstation e server.](../../standard/garbage-collection/workstation-server-gc.md)

I sottoprogusti della garbage collection sono di sfondo e non simultanei.

Utilizzare le impostazioni seguenti per selezionare le tà dei Garbage Collection:

### <a name="systemgcservercomplus_gcserver"></a>System.GC.Server/COMPlus_gcServer

- Configura se l'applicazione utilizza l'operazione di Garbage Collection per workstation o la procedura di Garbage Collection per server.
- Impostazione predefinita:`false`Operazione compensata workstation ( ).

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.Server` | `false`- stazione di lavoro<br/>`true`- server | .NET Core 1.0 |
| **MSBuild (proprietà)** | `ServerGarbageCollection` | `false`- stazione di lavoro<br/>`true`- server | .NET Core 1.0 |
| **Variabile di ambiente** | `COMPlus_gcServer` | `0`- stazione di lavoro<br/>`1`- server | .NET Core 1.0 |
| **app.config per .NET Framework** | [Server globale](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | `false`- stazione di lavoro<br/>`true`- server |  |

### <a name="examples"></a>Esempi

*runtimeconfig.json:*

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

File di progetto:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a>System.GC.Concurrent/COMPlus_gcConcurrent

- Configura se l'operazione di Garbage Collection in background (simultanea) è abilitata.
- Impostazione predefinita: Abilitato (`true`).
- Per ulteriori informazioni, consultate [Garbage Collection](../../standard/garbage-collection/background-gc.md)in background .

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.Concurrent` | `true`- sfondo GC<br/>`false`- GC non simultaneo | .NET Core 1.0 |
| **MSBuild (proprietà)** | `ConcurrentGarbageCollection` | `true`- sfondo GC<br/>`false`- GC non simultaneo | .NET Core 1.0 |
| **Variabile di ambiente** | `COMPlus_gcConcurrent` | `true`- sfondo GC<br/>`false`- GC non simultaneo | .NET Core 1.0 |
| **app.config per .NET Framework** | [gcConcurrent (corrente)](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | `true`- sfondo GC<br/>`false`- GC non simultaneo |  |

### <a name="examples"></a>Esempi

*runtimeconfig.json:*

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

File di progetto:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a>Gestire l'utilizzo delle risorse

Utilizzare le impostazioni descritte in questa sezione per gestire la memoria del Garbage Collector e l'utilizzo del processore.

Per ulteriori informazioni su alcune di queste impostazioni, vedere il punto [di mezzo tra workstation e server GC(](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) server).

### <a name="systemgcheapcountcomplus_gcheapcount"></a>System.GC.HeapCount/COMPlus_GCHeapCount

- Limita il numero di heap creati dal Garbage Collector.
- Si applica solo alla procedura di Garbage Collection per server.
- Se l'affinità [del processore GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) è abilitata, che `n` è l'impostazione predefinita, l'impostazione del numero di heap affina gli heap/thread GC ai primi `n` processori. Utilizzare le impostazioni [affinitize mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) o [affinitize ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) per specificare esattamente i processori di cui eseguire l'affinità.
- Se [l'affinità del processore GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) è disabilitata, questa impostazione limita il numero di heap GC.
- Per ulteriori informazioni, vedere le [osservazioni di GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapCount` | *valore decimale* | .NET Core 3.0 |
| **Variabile di ambiente** | `COMPlus_GCHeapCount` | *valore esadecimale* | .NET Core 3.0 |
| **app.config per .NET Framework** | [Metodo GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | *valore decimale* | .NET Framework 4.6.2 |

Esempio:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapCount": 16
      }
   }
}
```

> [!TIP]
> Se si imposta l'opzione in *runtimeconfig.json*, specificare un valore decimale. Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale. Ad esempio, per limitare il numero di heap a 16, i valori sarebbero 16 per il file JSON e 0x10 o 10 per la variabile di ambiente.

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a>System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask

- Specifica i processori esatti che i thread del Garbage Collector devono utilizzare.
- Se [l'affinità del processore GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) è disabilitata, questa impostazione viene ignorata.
- Si applica solo alla procedura di Garbage Collection per server.
- Il valore è una maschera di bit che definisce i processori disponibili per il processo. Ad esempio, un valore decimale di 1023 (o un valore esadecimale di 0x3FF o 3FF se si utilizza la variabile di ambiente) è 0011 1111 1111 in notazione binaria. Specifica che devono essere utilizzati i primi 10 processori. Per specificare i successivi 10 processori, ovvero processori 10-19, specificare un valore decimale di 1047552 (o un valore esadecimale di 0xFFC00 o FFC00), che equivale a un valore binario di 1111 1111 1100 0000 0000.

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapAffinitizeMask` | *valore decimale* | .NET Core 3.0 |
| **Variabile di ambiente** | `COMPlus_GCHeapAffinitizeMask` | *valore esadecimale* | .NET Core 3.0 |
| **app.config per .NET Framework** | [MASCHERAPer tuttaMaschera](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | *valore decimale* | .NET Framework 4.6.2 |

Esempio:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a>System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges

- Specifica l'elenco dei processori da utilizzare per i thread del Garbage Collector.
- Questa impostazione è simile a [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), ad eccezione del fatto che consente di specificare più di 64 processori.
- Per i sistemi operativi Windows, anteporre al numero o all'intervallo del processore il [gruppo di CPU](/windows/win32/procthread/processor-groups)corrispondente, ad esempio "0:1-10,0:12,1:50-52,1:70".
- Se [l'affinità del processore GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) è disabilitata, questa impostazione viene ignorata.
- Si applica solo alla procedura di Garbage Collection per server.
- Per ulteriori informazioni, consulta [Migliorare la configurazione della CPU per GC sulle macchine con > 64 CPU](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) nel blog di Maoni Stephens.

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.GCHeapAffinitizeRanges` | Elenco delimitato da virgole di numeri di processore o intervalli di numeri di processore.<br/>Esempio Unix: "1-10,12,50-52,70"<br/>Esempio di Windows: "0:1-10,0:12,1:50-52,1:70" | .NET Core 3.0 |
| **Variabile di ambiente** | `COMPlus_GCHeapAffinitizeRanges` | Elenco delimitato da virgole di numeri di processore o intervalli di numeri di processore.<br/>Esempio Unix: "1-10,12,50-52,70"<br/>Esempio di Windows: "0:1-10,0:12,1:50-52,1:70" | .NET Core 3.0 |

Esempio:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a>COMPlus_GCCpuGroup

- Configura se il Garbage Collector utilizza o meno [i gruppi della CPU.](/windows/win32/procthread/processor-groups)

  Quando un computer Windows a 64 bit dispone di più gruppi di CPU, ovvero sono presenti più di 64 processori, l'abilitazione di questo elemento estende la procedura di Garbage Collection in tutti i gruppi di CPU. Il Garbage Collector utilizza tutti i core per creare e bilanciare gli heap.

- Si applica alla procedura di Garbage Collection per server solo nei sistemi operativi Windows a 64 bit.
- Impostazione predefinita: Disabilitato (`0`).
- Per ulteriori informazioni, consulta [Migliorare la configurazione della CPU per GC sulle macchine con > 64 CPU](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) nel blog di Maoni Stephens.

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.json** | N/D | N/D | N/D |
| **Variabile di ambiente** | `COMPlus_GCCpuGroup` | `0`- disabilitato<br/>`1`- abilitato | .NET Core 1.0 |
| **app.config per .NET Framework** | [Gruppo GCCpuGroup](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | `false`- disabilitato<br/>`true`- abilitato |  |

> [!NOTE]
> Per configurare Common Language Runtime (CLR) per distribuire anche i thread dal pool di thread in tutti i gruppi di CPU, abilitare l'opzione [Thread_UseAllCpuGroups elemento.](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) Per le app .NET Core, è possibile abilitare questa opzione impostando il valore della variabile di `COMPlus_Thread_UseAllCpuGroups` ambiente su `1`.

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a>System.GC.NoAffinitize/COMPlus_GCNoAffinitize

- Specifica se *eseguire l'affinità* di thread di Garbage Collection con i processori. Per affinizzare un thread GC significa che può essere eseguito solo sulla CPU specifica. Viene creato un heap per ogni thread GC.
- Si applica solo alla procedura di Garbage Collection per server.
- Impostazione predefinita: affinizzare i thread`false`di Garbage Collection con processori ( ).

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.NoAffinitize` | `false`- affinizzare<br/>`true`- non affinizzare | .NET Core 3.0 |
| **Variabile di ambiente** | `COMPlus_GCNoAffinitize` | `0`- affinizzare<br/>`1`- non affinizzare | .NET Core 3.0 |
| **app.config per .NET Framework** | [GCNoAffinitize](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | `false`- affinizzare<br/>`true`- non affinizzare | .NET Framework 4.6.2 |

Esempio:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a>System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit

- Specifica la dimensione massima di commit, in byte, per l'heap GC e la contabilità GC.
- Questa impostazione si applica solo ai computer a 64 bit.
- Il valore predefinito, che si applica solo in alcuni casi, è il maggiore di 20 MB o il 75% del limite di memoria sul contenitore. Il valore predefinito viene applicato se:

  - Il processo è in esecuzione all'interno di un contenitore con un limite di memoria specificato.
  - [System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) non impostato.

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapHardLimit` | *valore decimale* | .NET Core 3.0 |
| **Variabile di ambiente** | `COMPlus_GCHeapHardLimit` | *valore esadecimale* | .NET Core 3.0 |

Esempio:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimit": 209715200
      }
   }
}
```

> [!TIP]
> Se si imposta l'opzione in *runtimeconfig.json*, specificare un valore decimale. Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale. Ad esempio, per specificare un limite rigido dell'heap di 200 mebibyte (MiB), i valori sarebbero 209715200 per il file JSON e 0xC8000000 o C800000 per la variabile di ambiente.

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a>System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent

- Specifica l'utilizzo consentito dell'heap GC come percentuale della memoria fisica totale.
- Se è impostato anche [System.GC.HeapHardLimit,](#systemgcheaphardlimitcomplus_gcheaphardlimit) questa impostazione viene ignorata.
- Questa impostazione si applica solo ai computer a 64 bit.
- Se il processo è in esecuzione all'interno di un contenitore con un limite di memoria specificato, la percentuale viene calcolata come percentuale di tale limite di memoria.
- Il valore predefinito, che si applica solo in alcuni casi, è il minore di 20 MB o il 75% del limite di memoria sul contenitore. Il valore predefinito viene applicato se:

  - Il processo è in esecuzione all'interno di un contenitore con un limite di memoria specificato.
  - [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) non impostato.

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapHardLimitPercent` | *valore decimale* | .NET Core 3.0 |
| **Variabile di ambiente** | `COMPlus_GCHeapHardLimitPercent` | *valore esadecimale* | .NET Core 3.0 |

Esempio:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimitPercent": 30
      }
   }
}
```

> [!TIP]
> Se si imposta l'opzione in *runtimeconfig.json*, specificare un valore decimale. Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale. Ad esempio, per limitare l'utilizzo dell'heap al 30%, i valori sarebbero 30 per il file JSON e 0x1E o 1E per la variabile di ambiente.

### <a name="systemgcretainvmcomplus_gcretainvm"></a>System.GC.RetainVM/COMPlus_GCRetainVM

- Configura se i segmenti che devono essere eliminati vengono inseriti in un elenco di standby per un utilizzo futuro o vengono rilasciati nuovamente al sistema operativo (OS).
- Impostazione predefinita: rilasciare i segmenti`false`al sistema operativo ( ).

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.RetainVM` | `false`- rilascio al sistema operativo<br/>`true`- messo in standby | .NET Core 1.0 |
| **MSBuild (proprietà)** | `RetainVMGarbageCollection` | `false`- rilascio al sistema operativo<br/>`true`- messo in standby | .NET Core 1.0 |
| **Variabile di ambiente** | `COMPlus_GCRetainVM` | `0`- rilascio al sistema operativo<br/>`1`- messo in standby | .NET Core 1.0 |

### <a name="examples"></a>Esempi

*runtimeconfig.json:*

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

File di progetto:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a>Pagine grandi

### <a name="complus_gclargepages"></a>COMPlus_GCLargePages

- Specifica se le pagine di grandi dimensioni devono essere utilizzate quando viene impostato un limite rigido dell'heap.
- Impostazione predefinita: Disabilitato (`0`).
- Questa è un'impostazione sperimentale.

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.json** | N/D | N/D | N/D |
| **Variabile di ambiente** | `COMPlus_GCLargePages` | `0`- disabilitato<br/>`1`- abilitato | .NET Core 3.0 |

## <a name="large-objects"></a>Oggetti di grandi dimensioni

### <a name="complus_gcallowverylargeobjects"></a>COMPlus_gcAllowVeryLargeObjects

- Configura il supporto del Garbage Collector su piattaforme a 64 bit per array di dimensioni superiori a 2 gigabyte (GB).
- Impostazione predefinita: Abilitato (`1`).
- Questa opzione potrebbe diventare obsoleta in una versione futura di .NET.

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.json** | N/D | N/D | N/D |
| **Variabile di ambiente** | `COMPlus_gcAllowVeryLargeObjects` | `1`- abilitato<br/> `0`- disabilitato | .NET Core 1.0 |
| **app.config per .NET Framework** | [gcAllowVeryLargeObjects](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | `1`- abilitato<br/> `0`- disabilitato | .NET Framework 4.5 |

## <a name="large-object-heap-threshold"></a>Soglia heap oggetti grandi

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a>System.GC.LOHSoglia/COMPlus_GCLOHThreshold

- Specifica la dimensione della soglia, in byte, che determina l'attivazione dell'heap oggetti grandi (LOH).
- La soglia predefinita è 85.000 byte.
- Il valore specificato deve essere maggiore della soglia predefinita.

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.LOHThreshold` | *valore decimale* | .NET Core 1.0 |
| **Variabile di ambiente** | `COMPlus_GCLOHThreshold` | *valore esadecimale* | .NET Core 1.0 |
| **app.config per .NET Framework** | [Soglia GCLOH](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | *valore decimale* | .NET Framework 4.8 |

Esempio:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.LOHThreshold": 120000
      }
   }
}
```

> [!TIP]
> Se si imposta l'opzione in *runtimeconfig.json*, specificare un valore decimale. Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale. Ad esempio, per impostare una dimensione di soglia di 120.000 byte, i valori sarebbero 120000 per il file JSON e 0x1D4C0 o 1D4C0 per la variabile di ambiente.

## <a name="standalone-gc"></a>GC autonomo

### <a name="complus_gcname"></a>COMPlus_GCName

- Specifica un percorso alla libreria contenente il Garbage Collector che il runtime intende caricare.
- Per ulteriori informazioni, consultate [Progettazione di caricatori GC autonomi.](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md)

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.json** | N/D | N/D | N/D |
| **Variabile di ambiente** | `COMPlus_GCName` | *string_path* | .NET Core 2.0 |
