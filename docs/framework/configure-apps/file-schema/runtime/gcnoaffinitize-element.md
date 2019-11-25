---
title: Elemento GCNoAffinitize
ms.date: 11/08/2019
helpviewer_keywords:
- gcNoAffinitize element
- <gcNoAffinitize> element
ms.openlocfilehash: 4031ff19131c905072696837d1622dbb6e54ae61
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978375"
---
# <a name="gcnoaffinitize-element"></a>\<elemento > GCNoAffinitize

Specifica se creare affinità tra i thread GC del server con CPU.

> di configurazione di \<\
&nbsp;&nbsp;\<Runtime > \
&nbsp;&nbsp;&nbsp;&nbsp;\<GCNoAffinitize >

## <a name="syntax"></a>Sintassi

```xml
<GCNoAffinitize
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

|Attributo|Descrizione|
|---------------|-----------------|
|`enabled`|Attributo obbligatorio.<br /><br />Specifica se i thread o gli heap GC del server sono creata un'affinità con i processori disponibili nel computer.|

#### <a name="enabled-attribute"></a>attributo enabled

|Value|Descrizione|
|-----------|-----------------|
|`false`|Thread GC del server cui con CPU. Questa è l'impostazione predefinita.|
|`true`|Non creare affinità tra i thread GC del server con CPU.|

### <a name="child-elements"></a>Elementi figlio

Nessuna.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|

## <a name="remarks"></a>Note

Per impostazione predefinita, i thread GC del server sono creata un'affinità con le rispettive CPU. Ogni processore disponibile del sistema dispone di un proprio heap GC e di un thread. Si tratta in genere dell'impostazione preferita perché ottimizza l'utilizzo della cache. A partire da .NET Framework 4.6.2, impostando l'attributo `enabled` dell'elemento **GCNoAffinitize** su `false`, è possibile specificare che le CPU e i thread GC del server non devono essere strettamente collegati.

È possibile specificare solo l'elemento di configurazione **GCNoAffinitize** per non creare affinità tra i thread GC del server con CPU. È anche possibile usarlo insieme all'elemento [GCHeapCount](gcheapcount-element.md) per controllare il numero di heap e thread GC usati da un'applicazione.

Se l'attributo `enabled` dell'elemento **GCNoAffinitize** è `false` (valore predefinito), è anche possibile usare l'elemento [GCHeapCount](gcheapcount-element.md) per specificare il numero di thread e heap GC, insieme all'elemento [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md) per specificare i processori a cui sono creata un'affinità i thread GC e gli heap.

## <a name="example"></a>Esempio

L'esempio seguente non creare affinità tra i thread GC del server:

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

L'esempio seguente non creare affinità tra i thread GC del server e limita il numero di heap GC/thread a 10:

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [Elemento GCHeapAffinitizeMask](gcheapaffinitizemask-element.md)
- [Elemento GCHeapCount](gcheapcount-element.md)
- [Principi fondamentali di Garbage Collection](../../../../standard/garbage-collection/fundamentals.md)
- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
