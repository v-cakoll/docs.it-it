---
title: Impostazioni di configurazione del Garbage Collector
description: Informazioni sulle impostazioni di run-time per la configurazione del modo in cui il Garbage Collector gestisce la memoria per le app .NET Core.
ms.date: 07/10/2020
ms.topic: reference
ms.openlocfilehash: 6ae5b7447fb0df4978ea9dcaa5e76fcc7a6cc4ca
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441407"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a>Opzioni di configurazione in fase di esecuzione per Garbage Collection

Questa pagina contiene informazioni sulle impostazioni di Garbage Collector (GC) che possono essere modificate in fase di esecuzione. Se si sta tentando di ottenere prestazioni ottimali di un'app in esecuzione, è consigliabile usare queste impostazioni. Tuttavia, le impostazioni predefinite forniscono prestazioni ottimali per la maggior parte delle applicazioni in situazioni tipiche.

Le impostazioni sono disposte in gruppi in questa pagina. Le impostazioni all'interno di ogni gruppo vengono comunemente usate insieme tra loro per ottenere un risultato specifico.

> [!NOTE]
>
> - Queste impostazioni possono essere modificate anche in modo dinamico dall'app mentre è in esecuzione, quindi è possibile eseguire l'override di tutte le impostazioni di runtime impostate.
> - Alcune impostazioni, ad esempio il [livello di latenza](../../standard/garbage-collection/latency.md), vengono in genere impostate solo tramite l'API in fase di progettazione. Tali impostazioni vengono omesse da questa pagina.
> - Per i valori numerici, usare la notazione decimale per le impostazioni nel *runtimeconfig.jssu* file e la notazione esadecimale per le impostazioni delle variabili di ambiente. Per i valori esadecimali, è possibile specificarli con o senza il prefisso "0x".

## <a name="flavors-of-garbage-collection"></a>Tipi di Garbage Collection

I due principali tipi di Garbage Collection sono GC della workstation e GC del server. Per ulteriori informazioni sulle differenze tra le due, vedere [workstation e server Garbage Collection](../../standard/garbage-collection/workstation-server-gc.md).

Le sottoversioni di Garbage Collection sono in background e non simultanee.

Usare le impostazioni seguenti per selezionare le versioni di Garbage Collection:

### <a name="systemgcservercomplus_gcserver"></a>System. GC. Server/COMPlus_gcServer

- Configura se l'applicazione utilizza la workstation Garbage Collection o Garbage Collection server.
- Impostazione predefinita: Garbage Collection workstation. Equivale a impostare il valore su `false` .

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.js** | `System.GC.Server` | `false`-workstation<br/>`true`-Server | .NET Core 1.0 |
| **MSBuild (proprietà)** | `ServerGarbageCollection` | `false`-workstation<br/>`true`-Server | .NET Core 1.0 |
| **Variabile di ambiente** | `COMPlus_gcServer` | `0`-workstation<br/>`1`-Server | .NET Core 1.0 |
| **app.config per .NET Framework** | [GCServer](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | `false`-workstation<br/>`true`-Server |  |

### <a name="examples"></a>Esempio

*runtimeconfig.jsnel* file:

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

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a>System. GC. Concurrent/COMPlus_gcConcurrent

- Configura se la Garbage Collection di sfondo (simultanea) è abilitata.
- Impostazione predefinita: USA GC in background. Equivale a impostare il valore su `true` .
- Per ulteriori informazioni, vedere [Background Garbage Collection](../../standard/garbage-collection/background-gc.md).

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.js** | `System.GC.Concurrent` | `true`-GC in background<br/>`false`-GC non simultanei | .NET Core 1.0 |
| **MSBuild (proprietà)** | `ConcurrentGarbageCollection` | `true`-GC in background<br/>`false`-GC non simultanei | .NET Core 1.0 |
| **Variabile di ambiente** | `COMPlus_gcConcurrent` | `1`-GC in background<br/>`0`-GC non simultanei | .NET Core 1.0 |
| **app.config per .NET Framework** | [gcConcurrent](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | `true`-GC in background<br/>`false`-GC non simultanei |  |

### <a name="examples"></a>Esempio

*runtimeconfig.jsnel* file:

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

Usare le impostazioni descritte in questa sezione per gestire l'utilizzo della memoria e del processore del Garbage Collector.

Per altre informazioni su alcune di queste impostazioni, vedere la parte intermedia tra la voce del Blog di [GC workstation e server](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) .

### <a name="systemgcheapcountcomplus_gcheapcount"></a>System. GC. HeapCount/COMPlus_GCHeapCount

- Limita il numero di heap creati dal Garbage Collector.
- Si applica solo al server Garbage Collection.
- Se è abilitata l' [affinità processori GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) , che è l'impostazione predefinita, il numero di heap imposta cui `n` GC Heaps/Threads sui primi `n` processori. Usare le impostazioni [creare affinità tra mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) o [creare affinità tra Ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) per specificare esattamente i processori da creare affinità tra.
- Se l' [affinità processori GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) è disabilitata, questa impostazione limita il numero di heap GC.
- Per ulteriori informazioni, vedere la [sezione Osservazioni GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.js** | `System.GC.HeapCount` | *valore decimale* | .NET Core 3.0 |
| **Variabile di ambiente** | `COMPlus_GCHeapCount` | *valore esadecimale* | .NET Core 3.0 |
| **app.config per .NET Framework** | [GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | *valore decimale* | .NET Framework 4.6.2 |

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
> Se si sta impostando l'opzione in *runtimeconfig.json*, specificare un valore decimale. Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale. Ad esempio, per limitare il numero di heap a 16, i valori sarebbero 16 per il file JSON e 0x10 o 10 per la variabile di ambiente.

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a>System. GC. HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask

- Specifica i processori esatti che Garbage Collector thread devono usare.
- Se l' [affinità processori GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) è disabilitata, questa impostazione viene ignorata.
- Si applica solo al server Garbage Collection.
- Il valore è una maschera di bit che definisce i processori disponibili per il processo. Ad esempio, un valore decimale di 1023 (o un valore esadecimale di 0x3FF o 3FF se si usa la variabile di ambiente) è 0011 1111 1111 in notazione binaria. Specifica che devono essere usati i primi 10 processori. Per specificare i 10 processori successivi, ovvero i processori 10-19, specificare un valore decimale di 1047552 (o un valore esadecimale di 0xFFC00 o FFC00), equivalente a un valore binario di 1111 1111 1100 0000 0000.

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.js** | `System.GC.HeapAffinitizeMask` | *valore decimale* | .NET Core 3.0 |
| **Variabile di ambiente** | `COMPlus_GCHeapAffinitizeMask` | *valore esadecimale* | .NET Core 3.0 |
| **app.config per .NET Framework** | [GCHeapAffinitizeMask](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | *valore decimale* | .NET Framework 4.6.2 |

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

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a>System. GC. GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges

- Specifica l'elenco di processori da usare per Garbage Collector thread.
- Questa impostazione è simile a [System. GC. HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), con la differenza che consente di specificare più di 64 processori.
- Per i sistemi operativi Windows, anteporre al [gruppo di CPU](/windows/win32/procthread/processor-groups)corrispondente il numero o l'intervallo del processore, ad esempio "0:1-10, 0:12, 1:50-52, 1:70".
- Se l' [affinità processori GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) è disabilitata, questa impostazione viene ignorata.
- Si applica solo al server Garbage Collection.
- Per altre informazioni, vedere [migliorare la configurazione della CPU per GC nei computer con > cpu 64](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) nel Blog di Maoni Stephens.

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.js** | `System.GC.GCHeapAffinitizeRanges` | Elenco delimitato da virgole di numeri di processore o intervalli di numeri del processore.<br/>Esempio di UNIX: "1-10, 12, 50-52, 70"<br/>Esempio di Windows: "0:1-10, 0:12, 1:50-52, 1:70" | .NET Core 3.0 |
| **Variabile di ambiente** | `COMPlus_GCHeapAffinitizeRanges` | Elenco delimitato da virgole di numeri di processore o intervalli di numeri del processore.<br/>Esempio di UNIX: "1-10, 12, 50-52, 70"<br/>Esempio di Windows: "0:1-10, 0:12, 1:50-52, 1:70" | .NET Core 3.0 |

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

- Configura se il Garbage Collector utilizza o meno [gruppi di CPU](/windows/win32/procthread/processor-groups) .

  Quando un computer Windows a 64 bit dispone di più gruppi di CPU, ovvero sono presenti più di 64 processori, l'abilitazione di questo elemento estende Garbage Collection in tutti i gruppi di CPU. Il Garbage Collector utilizza tutti i core per creare e bilanciare gli heap.

- Si applica al server Garbage Collection solo nei sistemi operativi Windows a 64 bit.
- Impostazione predefinita: GC non si estende tra gruppi di CPU. Equivale a impostare il valore su `0` .
- Per altre informazioni, vedere [migliorare la configurazione della CPU per GC nei computer con > cpu 64](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) nel Blog di Maoni Stephens.

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.js** | N/D | N/D | N/D |
| **Variabile di ambiente** | `COMPlus_GCCpuGroup` | `0`-disabilitato<br/>`1`-abilitato | .NET Core 1.0 |
| **app.config per .NET Framework** | [GCCpuGroup](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | `false`-disabilitato<br/>`true`-abilitato |  |

> [!NOTE]
> Per configurare il Common Language Runtime (CLR) in modo da distribuire anche i thread dal pool di thread in tutti i gruppi di CPU, abilitare l'opzione [elemento Thread_UseAllCpuGroups](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) . Per le app .NET Core, è possibile abilitare questa opzione impostando il valore della `COMPlus_Thread_UseAllCpuGroups` variabile di ambiente su `1` .

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a>System. GC. NoAffinitize/COMPlus_GCNoAffinitize

- Specifica se *creare affinità tra* Garbage Collection thread con i processori. Per creare affinità tra un thread GC significa che può essere eseguito solo sulla CPU specifica. Viene creato un heap per ogni thread GC.
- Si applica solo al server Garbage Collection.
- Impostazione predefinita: creare affinità tra Garbage Collection thread con processori. Equivale a impostare il valore su `false` .

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.js** | `System.GC.NoAffinitize` | `false`-creare affinità tra<br/>`true`-non creare affinità tra | .NET Core 3.0 |
| **Variabile di ambiente** | `COMPlus_GCNoAffinitize` | `0`-creare affinità tra<br/>`1`-non creare affinità tra | .NET Core 3.0 |
| **app.config per .NET Framework** | [GCNoAffinitize](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | `false`-creare affinità tra<br/>`true`-non creare affinità tra | .NET Framework 4.6.2 |

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

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a>System. GC. HeapHardLimit/COMPlus_GCHeapHardLimit

- Specifica la dimensione massima del commit, in byte, per l'heap GC e la contabilità GC.
- Questa impostazione si applica solo ai computer a 64 bit.
- Questa impostazione viene ignorata se sono configurati i [limiti dell'heap per oggetto](#per-object-heap-limits) .
- Il valore predefinito, applicabile solo in alcuni casi, è maggiore di 20 MB o del 75% del limite di memoria nel contenitore. Il valore predefinito si applica se:

  - Il processo è in esecuzione all'interno di un contenitore con un limite di memoria specificato.
  - [System. GC. HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) non è impostato.

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.js** | `System.GC.HeapHardLimit` | *valore decimale* | .NET Core 3.0 |
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
> Se si sta impostando l'opzione in *runtimeconfig.json*, specificare un valore decimale. Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale. Ad esempio, per specificare un limite rigido dell'heap di 200 mebibytes (MiB), i valori sarebbero 209715200 per il file JSON e 0xC800000 o C800000 per la variabile di ambiente.

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a>System. GC. HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent

- Specifica l'utilizzo dell'heap GC consentito come percentuale della memoria fisica totale.
- Se viene impostato anche [System. GC. HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) , questa impostazione viene ignorata.
- Questa impostazione si applica solo ai computer a 64 bit.
- Se il processo è in esecuzione all'interno di un contenitore con un limite di memoria specificato, la percentuale viene calcolata come percentuale del limite di memoria.
- Questa impostazione viene ignorata se sono configurati i [limiti dell'heap per oggetto](#per-object-heap-limits) .
- Il valore predefinito, applicabile solo in alcuni casi, è minore di 20 MB o del 75% del limite di memoria nel contenitore. Il valore predefinito si applica se:

  - Il processo è in esecuzione all'interno di un contenitore con un limite di memoria specificato.
  - [System. GC. HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) non è impostato.

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.js** | `System.GC.HeapHardLimitPercent` | *valore decimale* | .NET Core 3.0 |
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
> Se si sta impostando l'opzione in *runtimeconfig.json*, specificare un valore decimale. Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale. Ad esempio, per limitare l'utilizzo dell'heap al 30%, i valori sarebbero 30 per il file JSON e 0x1E o 1E per la variabile di ambiente.

### <a name="per-object-heap-limits"></a>Limiti per oggetto-heap

È possibile specificare l'utilizzo dell'heap consentito del GC in base all'heap degli oggetti. Gli heap diversi sono l'heap degli oggetti grandi (LOH), l'heap degli oggetti piccoli (SOH) e l'heap degli oggetti bloccati.

#### <a name="complus_gcheaphardlimitsoh-complus_gcheaphardlimitloh-complus_gcheaphardlimitpoh"></a>COMPLUS_GCHeapHardLimitSOH, COMPLUS_GCHeapHardLimitLOH, COMPLUS_GCHeapHardLimitPOH

- Se si specifica un valore per le `COMPLUS_GCHeapHardLimitSOH` `COMPLUS_GCHeapHardLimitLOH` Impostazioni, o `COMPLUS_GCHeapHardLimitPOH` , è necessario specificare anche un valore per `COMPLUS_GCHeapHardLimitSOH` e `COMPLUS_GCHeapHardLimitLOH` . In caso contrario, il runtime non verrà inizializzato.
- Il valore predefinito per `COMPLUS_GCHeapHardLimitPOH` è 0. `COMPLUS_GCHeapHardLimitSOH`e `COMPLUS_GCHeapHardLimitLOH` non hanno valori predefiniti.

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **Variabile di ambiente** | `COMPLUS_GCHeapHardLimitSOH` | *valore esadecimale* | .NET 5,0 |
| **Variabile di ambiente** | `COMPLUS_GCHeapHardLimitLOH` | *valore esadecimale* | .NET 5,0 |
| **Variabile di ambiente** | `COMPLUS_GCHeapHardLimitPOH` | *valore esadecimale* | .NET 5,0 |

> [!TIP]
> Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale. Per specificare, ad esempio, un limite rigido dell'heap di 200 mebibytes (MiB), il valore sarà 0xC800000 o C800000.

#### <a name="complus_gcheaphardlimitsohpercent-complus_gcheaphardlimitlohpercent-complus_gcheaphardlimitpohpercent"></a>COMPLUS_GCHeapHardLimitSOHPercent, COMPLUS_GCHeapHardLimitLOHPercent, COMPLUS_GCHeapHardLimitPOHPercent

- Se si specifica un valore per le `COMPLUS_GCHeapHardLimitSOHPercent` `COMPLUS_GCHeapHardLimitLOHPercent` Impostazioni, o `COMPLUS_GCHeapHardLimitPOHPercent` , è necessario specificare anche un valore per `COMPLUS_GCHeapHardLimitSOHPercent` e `COMPLUS_GCHeapHardLimitLOHPercent` . In caso contrario, il runtime non verrà inizializzato.
- Queste impostazioni vengono ignorate `COMPLUS_GCHeapHardLimitSOH` se `COMPLUS_GCHeapHardLimitLOH` `COMPLUS_GCHeapHardLimitPOH` vengono specificati, e.
- Il valore 1 indica che GC utilizza l'1% della memoria fisica totale per l'heap degli oggetti.
- Ogni valore deve essere maggiore di zero e minore di 100. Inoltre, la somma dei tre valori di percentuale deve essere minore di 100. In caso contrario, il runtime non verrà inizializzato.

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **Variabile di ambiente** | `COMPLUS_GCHeapHardLimitSOHPercent` | *valore esadecimale* | .NET 5,0 |
| **Variabile di ambiente** | `COMPLUS_GCHeapHardLimitLOHPercent` | *valore esadecimale* | .NET 5,0 |
| **Variabile di ambiente** | `COMPLUS_GCHeapHardLimitPOHPercent` | *valore esadecimale* | .NET 5,0 |

> [!TIP]
> Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale. Ad esempio, per limitare l'utilizzo dell'heap al 30%, il valore sarà 0x1E o 1E.

### <a name="systemgcretainvmcomplus_gcretainvm"></a>System. GC. RetainVM/COMPlus_GCRetainVM

- Configura se i segmenti da eliminare vengono inseriti in un elenco di standby per un uso futuro o vengono rilasciati al sistema operativo.
- Impostazione predefinita: rilascia i segmenti al sistema operativo. Equivale a impostare il valore su `false` .

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.js** | `System.GC.RetainVM` | `false`-versione a sistema operativo<br/>`true`-messa in standby | .NET Core 1.0 |
| **MSBuild (proprietà)** | `RetainVMGarbageCollection` | `false`-versione a sistema operativo<br/>`true`-messa in standby | .NET Core 1.0 |
| **Variabile di ambiente** | `COMPlus_GCRetainVM` | `0`-versione a sistema operativo<br/>`1`-messa in standby | .NET Core 1.0 |

### <a name="examples"></a>Esempio

*runtimeconfig.jsnel* file:

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

## <a name="large-pages"></a>Pagine di grandi dimensioni

### <a name="complus_gclargepages"></a>COMPlus_GCLargePages

- Specifica se le pagine di grandi dimensioni devono essere utilizzate quando viene impostato un limite rigido dell'heap.
- Impostazione predefinita: non utilizzare pagine di grandi dimensioni quando è impostato un limite rigido dell'heap. Equivale a impostare il valore su `0` .
- Si tratta di un'impostazione sperimentale.

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.js** | N/D | N/D | N/D |
| **Variabile di ambiente** | `COMPlus_GCLargePages` | `0`-disabilitato<br/>`1`-abilitato | .NET Core 3.0 |

## <a name="large-objects"></a>Oggetti di grandi dimensioni

### <a name="complus_gcallowverylargeobjects"></a>COMPlus_gcAllowVeryLargeObjects

- Configura Garbage Collector il supporto per le piattaforme a 64 bit per le matrici con dimensione totale superiore a 2 gigabyte (GB).
- Impostazione predefinita: GC supporta matrici di dimensioni maggiori di 2 GB. Equivale a impostare il valore su `1` .
- Questa opzione potrebbe diventare obsoleta in una versione futura di .NET.

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.js** | N/D | N/D | N/D |
| **Variabile di ambiente** | `COMPlus_gcAllowVeryLargeObjects` | `1`-abilitato<br/> `0`-disabilitato | .NET Core 1.0 |
| **app.config per .NET Framework** | [gcAllowVeryLargeObjects](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | `1`-abilitato<br/> `0`-disabilitato | .NET Framework 4.5 |

## <a name="large-object-heap-threshold"></a>Soglia heap oggetti grandi

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a>System. GC. LOHThreshold/COMPlus_GCLOHThreshold

- Specifica le dimensioni della soglia, in byte, che determinano l'uso degli oggetti nell'heap degli oggetti grandi (LOH).
- La soglia predefinita è 85.000 byte.
- Il valore specificato deve essere maggiore della soglia predefinita.

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.js** | `System.GC.LOHThreshold` | *valore decimale* | .NET Core 1.0 |
| **Variabile di ambiente** | `COMPlus_GCLOHThreshold` | *valore esadecimale* | .NET Core 1.0 |
| **app.config per .NET Framework** | [GCLOHThreshold](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | *valore decimale* | .NET Framework 4.8 |

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
> Se si sta impostando l'opzione in *runtimeconfig.json*, specificare un valore decimale. Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale. Ad esempio, per impostare una dimensione della soglia di 120.000 byte, i valori sarebbero 120000 per il file JSON e 0x1D4C0 o 1D4C0 per la variabile di ambiente.

## <a name="standalone-gc"></a>GC autonomo

### <a name="complus_gcname"></a>COMPlus_GCName

- Specifica un percorso della libreria che contiene il Garbage Collector che il runtime intende caricare.
- Per ulteriori informazioni, vedere la pagina relativa alla [progettazione del caricatore GC autonomo](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).

| | Nome impostazione | Valori | Versione introdotta |
| - | - | - | - |
| **runtimeconfig.js** | N/D | N/D | N/D |
| **Variabile di ambiente** | `COMPlus_GCName` | *string_path* | .NET Core 2.0 |
