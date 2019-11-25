---
title: Elemento gcConcurrent
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
ms.openlocfilehash: 5957337aa960a0d5f445249b410dbfaddb7b08e9
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73969225"
---
# <a name="gcconcurrent-element"></a>\<elemento > gcConcurrent

Specifica se in Common Language Runtime viene eseguita una procedura di Garbage Collection in un thread separato.

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime >](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<gcConcurrent >

## <a name="syntax"></a>Sintassi

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

|Attributo|Descrizione|
|---------------|-----------------|
|`enabled`|Attributo obbligatorio.<br /><br />Specifica se il runtime esegue operazioni di Garbage Collection simultaneamente.|

#### <a name="enabled-attribute"></a>attributo enabled

|Value|Descrizione|
|-----------|-----------------|
|`false`|Non viene eseguito Garbage Collection simultaneamente.|
|`true`|Viene eseguita la procedura di Garbage Collection in modo concorrente. Questa è l'impostazione predefinita.|

### <a name="child-elements"></a>Elementi figlio

Nessuna.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|

## <a name="remarks"></a>Note

Prima di .NET Framework 4, la workstation Garbage Collection supportava Garbage Collection simultanee, che eseguivano Garbage Collection in background in un thread separato. In .NET Framework 4, il Garbage Collection simultaneo è stato sostituito da GC in background, che esegue anche Garbage Collection in background in un thread separato. A partire da .NET Framework 4,5, la raccolta in background è diventata disponibile nell'Garbage Collection server. L'elemento **gcConcurrent** controlla se il runtime esegue le Garbage Collection simultanee o in background, se disponibile, o se esegue Garbage Collection in primo piano.

### <a name="to-disable-background-garbage-collection"></a>Per disabilitare lo sfondo Garbage Collection

> [!WARNING]
> A partire da .NET Framework 4, il Garbage Collection simultaneo viene sostituito da Garbage Collection in background. I termini *simultanei* e in *background* vengono usati in modo interscambiabile nella documentazione di .NET Framework. Per disabilitare Garbage Collection in background, usare l'elemento **gcConcurrent** , come descritto in questo articolo.

Per impostazione predefinita, il runtime usa la Garbage Collection in modalità simultanea che è ottimizzata per la latenza. Se si usa un'applicazione che prevede una notevole interazione da parte dell'utente, non disabilitare l'esecuzione simultanea di Garbage Collection in modo da ridurre il tempo di sospensione dell'applicazione durante l'esecuzione di Garbage Collection. Se si imposta l'attributo `enabled` dell'elemento **gcConcurrent** su `false`, il runtime USA Garbage Collection non simultanee, che è ottimizzato per la velocità effettiva.

Il file di configurazione seguente Disabilita Garbage Collection di sfondo:

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

Se è presente un'impostazione **gcConcurrentSetting** nel file di configurazione del computer, definisce il valore predefinito per tutte le applicazioni .NET Framework. Con l'impostazione del file di configurazione del computer viene eseguito l'override dell'impostazione del file di configurazione dell'applicazione.

Per altre informazioni sulle Garbage Collection simultanee e in background, vedere le sezioni [Garbage Collection simultanea](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection), [Garbage Collection workstation in background](../../../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection)e [server in background Garbage Collection](../../../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection) nell'articolo [nozioni fondamentali di Garbage Collection](../../../../standard/garbage-collection/fundamentals.md) .

## <a name="example"></a>Esempio

Nell'esempio seguente viene abilitata la Garbage Collection in background:

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
- [Principi fondamentali di Garbage Collection](../../../../standard/garbage-collection/fundamentals.md)
