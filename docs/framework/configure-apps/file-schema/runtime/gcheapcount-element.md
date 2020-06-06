---
title: Elemento GCHeapCount
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 3d6cac4185af182758cb82e6bfd9d96ed24869b4
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74283078"
---
# <a name="gcheapcount-element"></a>Elemento \<GCHeapCount>

Specifica il numero di heap/thread da usare per il Garbage Collection server.

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapCount>

## <a name="syntax"></a>Sintassi

```xml
<GCHeapCount
   enabled="nn"/>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

|Attributo|Descrizione|
|---------------|-----------------|
|`enabled`|Attributo obbligatorio.<br /><br />Specifica il numero di heap da usare per il Garbage Collection server. Il numero effettivo di heap è il numero minimo di heap specificato e il numero di processori che il processo è autorizzato a utilizzare. |

#### <a name="enabled-attribute"></a>attributo enabled

|Valore|Description|
|-----------|-----------------|
|`nn`|Numero di heap da utilizzare per GC del server.|

### <a name="child-elements"></a>Elementi figlio

No.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|

## <a name="remarks"></a>Commenti

Per impostazione predefinita, i thread GC del server sono creata un'affinità con la rispettiva CPU, in modo da avere un heap GC, un thread GC server e un thread GC del server in background per ogni processore. A partire da .NET Framework 4.6.2, è possibile usare l'elemento **GCHeapCount** per limitare il numero di heap usati dall'applicazione per il Garbage Collector del server. La limitazione del numero di heap utilizzati per il Garbage Collector del server è particolarmente utile per i sistemi che eseguono più istanze di un'applicazione server.

**GCHeapCount** viene in genere usato insieme ad altri due flag:

- [GCNoAffinitize](gcnoaffinitize-element.md), che controlla se i thread o gli heap GC del server sono creata un'affinità con CPU.

- [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), che controlla l'affinità dei thread GC/heap con le CPU.

Se **GCHeapCount** è impostato e **GCNoAffinitize** è disabilitato (impostazione predefinita), esiste un'affinità tra i thread GC/heap *nn* e i primi processori *nn* . È possibile utilizzare l'elemento **GCHeapAffinitizeMask** per specificare quali processori vengono utilizzati dagli heap GC del server del processo. In caso contrario, se più processi server sono in esecuzione in un sistema, l'utilizzo del processore si sovrappone.

Se **GCHeapCount** è impostato e **GCNoAffinitize** è abilitato, il Garbage Collector limita il numero di processori utilizzati per il catalogo globale del server, ma non creare affinità tra gli heap GC e i processori.

## <a name="example"></a>Esempio

Nell'esempio seguente viene indicato che un'applicazione utilizza GC server con 10 heap/thread. Poiché non si vuole che tali heap si sovrappongano con gli heap di altre applicazioni in esecuzione nel sistema, usare **GCHeapAffinitizeMask** per specificare che il processo deve usare le CPU da 0 a 9.

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

L'esempio seguente non creare affinità tra i thread GC del server e limita il numero di heap GC/thread a 10.

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Vedi anche

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [Elemento GCNoAffinitize](gcnoaffinitize-element.md)
- [Elemento GCHeapAffinitizeMask](gcheapaffinitizemask-element.md)
- [Nozioni fondamentali di Garbage Collection](../../../../standard/garbage-collection/fundamentals.md)
- [Schema delle impostazioni di runtime](index.md)
- [Schema del file di configurazione](../index.md)
