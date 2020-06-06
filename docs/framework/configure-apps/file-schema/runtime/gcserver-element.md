---
title: Elemento gcServer
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer
helpviewer_keywords:
- gcServer element
- <gcServer> element
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
ms.openlocfilehash: 8eab5e36bab90510aff4f1a3e15328197ac59ed7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73968940"
---
# <a name="gcserver-element"></a>Elemento \<gcServer>

Specifica se Common Language Runtime esegue Garbage Collection per server.

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<gcServer>

## <a name="syntax"></a>Sintassi

```xml
<gcServer
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

|Attributo|Descrizione|
|---------------|-----------------|
|`enabled`|Attributo obbligatorio.<br /><br />Specifica se il runtime esegue Garbage Collection per server.|

#### <a name="enabled-attribute"></a>attributo enabled

|Valore|Description|
|-----------|-----------------|
|`false`|Non esegue Garbage Collection per server. Questo è il valore predefinito.|
|`true`|Esegue Garbage Collection per server.|

### <a name="child-elements"></a>Elementi figlio

No.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|

## <a name="remarks"></a>Commenti

Common Language Runtime (CLR) supporta due tipi di Garbage Collection: Garbage Collection per workstation, disponibile in tutti i sistemi, e Garbage Collection per server, disponibile nei sistemi con più processori. Utilizzare l'elemento **gcserver** per controllare il tipo di Garbage Collection eseguita da CLR. Usare la proprietà <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> per determinare se l'operazione Garbage Collection per server è abilitata.

Per i computer con un solo processore, l'operazione di Garbage Collection per workstation predefinita dovrebbe essere l'opzione più rapida. Per i computer con due processori, si può usare quella per workstation o quella per server. L'operazione di Garbage Collection per server dovrebbe essere l'opzione più rapida per più di due processori. In genere, i sistemi server multiprocessore disabilitano GC server e utilizzano GC workstation quando molte istanze di un'app Server vengono eseguite nello stesso computer.

Questo elemento può essere usato solo nel file di configurazione dell'applicazione. Se è nel file di configurazione del computer, viene ignorato.

> [!NOTE]
> In .NET Framework 4 e versioni precedenti, la modalità di Garbage Collection simultanea non è disponibile quando l'operazione di Garbage Collection per server è abilitata. A partire da .NET Framework 4.5, l'operazione di Garbage Collection per server è simultanea. Per utilizzare il Garbage Collection server non simultaneo, impostare l'elemento **gcserver** su `true` e l' [elemento gcConcurrent](gcconcurrent-element.md) su `false` .

A partire da .NET Framework 4.6.2, è anche possibile usare gli elementi seguenti per configurare GC del server:

- [GCNoAffinitize](gcnoaffinitize-element.md), che specifica se esiste un'affinità tra gli heap GC del server e i processori. Per impostazione predefinita, esiste un heap GC server per ogni processore.

- [GCHeapCount](gcheapcount-element.md), che limita il numero di heap utilizzati da un processo.

- [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), che definisce l'affinità tra gli heap GC del server disponibili e i singoli processori.

## <a name="example"></a>Esempio

Nell'esempio seguente viene abilitata l'Garbage Collection server:

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Vedi anche

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [Schema delle impostazioni di runtime](index.md)
- [Schema del file di configurazione](../index.md)
- [Per disabilitare Garbage Collection simultanee](gcconcurrent-element.md#to-disable-background-garbage-collection)
