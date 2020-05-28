---
title: Elemento GCNoAffinitize
ms.date: 11/08/2019
helpviewer_keywords:
- gcNoAffinitize element
- <gcNoAffinitize> element
ms.openlocfilehash: 16d6e5adefe2b632d7251669650058d7df7cea70
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004738"
---
# <a name="gcnoaffinitize-element"></a>elemento \<GCNoAffinitize>

Specifica se creare affinità tra i thread GC del server con CPU.

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCNoAffinitize>

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

|valore|Description|
|-----------|-----------------|
|`false`|Thread GC del server cui con CPU. Questo è il valore predefinito.|
|`true`|Non creare affinità tra i thread GC del server con CPU.|

### <a name="child-elements"></a>Elementi figlio

No.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|

## <a name="remarks"></a>Commenti

Per impostazione predefinita, i thread GC del server sono creata un'affinità con le rispettive CPU. Ogni processore disponibile del sistema dispone di un proprio heap GC e di un thread. Si tratta in genere dell'impostazione preferita perché ottimizza l'utilizzo della cache. A partire da .NET Framework 4.6.2, impostando l'attributo dell'elemento **GCNoAffinitize** `enabled` su `true` , è possibile specificare che i thread GC del server e le CPU non devono essere strettamente accoppiati.

È possibile specificare solo l'elemento di configurazione **GCNoAffinitize** per non creare affinità tra i thread GC del server con CPU. È anche possibile usarlo insieme all'elemento [GCHeapCount](gcheapcount-element.md) per controllare il numero di heap e thread GC usati da un'applicazione.

Se l' `enabled` attributo dell'elemento **GCNoAffinitize** è `false` (valore predefinito), è anche possibile usare l'elemento [GCHeapCount](gcheapcount-element.md) per specificare il numero di thread e heap GC, insieme all'elemento [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md) per specificare i processori a cui sono creata un'affinità i thread GC e gli heap.

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
- [Nozioni fondamentali di Garbage Collection](../../../../standard/garbage-collection/fundamentals.md)
- [Schema delle impostazioni di runtime](index.md)
- [Schema del file di configurazione](../index.md)
