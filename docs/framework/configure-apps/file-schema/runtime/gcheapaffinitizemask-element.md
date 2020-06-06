---
title: Elemento GCHeapAffinitizeMask
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 09d6523fb10692dd3617a3827d5bccf112bc632b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73978382"
---
# <a name="gcheapaffinitizemask-element"></a>Elemento \<GCHeapAffinitizeMask>

Definisce l'affinità tra heap GC e singoli processori.

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapAffinitizeMask>

## <a name="syntax"></a>Sintassi

```xml
<GCHeapAffinitizeMask
   enabled="nnnn"/>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

|Attributo|Descrizione|
|---------------|-----------------|
|`enabled`|Attributo obbligatorio.<br /><br />Specifica l'affinità tra heap GC e singoli processori. |

#### <a name="enabled-attribute"></a>attributo enabled

|Valore|Description|
|-----------|-----------------|
|`nnnn`|Valore decimale che costituisce una maschera di maschera che definisce l'affinità tra heap GC del server e singoli processori. |

### <a name="child-elements"></a>Elementi figlio

No.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|

## <a name="remarks"></a>Commenti

Per impostazione predefinita, i thread GC del server sono creata un'affinità con la rispettiva CPU, in modo da avere un heap GC, un thread GC server e un thread GC del server in background per ogni processore. A partire da .NET Framework 4.6.2, è possibile usare l'elemento **GCHeapAffinitizeMask** per controllare l'affinità tra gli heap e i processori GC del server quando il numero di heap è limitato dall'elemento **GCHeapCount** .

**GCHeapAffinitizeMask** viene in genere usato insieme ad altri due flag:

- [GCNoAffinitize](gcnoaffinitize-element.md), che controlla se i thread o gli heap GC del server sono creata un'affinità con CPU. L' `enabled` attributo dell'elemento [GCNoAffinitize](gcnoaffinitize-element.md) deve essere `false` (il valore predefinito) per l'impostazione **GCHeapAffinitizeMask** da usare.

- [GCHeapCount](gcheapcount-element.md), che limita il numero di heap utilizzati dal processo per il Garbage Collector del server. Per impostazione predefinita, è presente un heap per ogni processore.

**nnnn** è una maschera di bit espressa come valore decimale. Il bit 0 del byte 0 rappresenta il processore 0, il bit 1 di byte 0 rappresenta il processore 1 e così via. Ad esempio:

```xml
<GCHeapAffinitizeMask enabled="1023"/>
```

Il valore 1023 è 0x3FF o 0011 1111 1111b. Il processo utilizza 10 processori, dal processore 0 al processore 9.

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

## <a name="see-also"></a>Vedi anche

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [Elemento GCNoAffinitize](gcnoaffinitize-element.md)
- [Elemento GCHeapCount](gcheapcount-element.md)
- [Nozioni fondamentali di Garbage Collection](../../../../standard/garbage-collection/fundamentals.md)
- [Schema delle impostazioni di runtime](index.md)
- [Schema del file di configurazione](../index.md)
