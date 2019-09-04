---
title: <gcConcurrent> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b2774c32b4ee3e67772f84d599ecc5dbeb6598b
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252584"
---
# <a name="gcconcurrent-element"></a>\<Elemento > gcConcurrent

Specifica se in Common Language Runtime viene eseguita una procedura di Garbage Collection in un thread separato.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> di runtime**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<gcConcurrent>**  

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
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se il runtime esegue operazioni di Garbage Collection simultaneamente.|

## <a name="enabled-attribute"></a>attributo enabled

|Valore|Descrizione|
|-----------|-----------------|
|`false`|Non viene eseguito Garbage Collection simultaneamente.|
|`true`|Viene eseguita la procedura di Garbage Collection in modo concorrente. Questa è l'impostazione predefinita.|

### <a name="child-elements"></a>Elementi figlio

Nessuno.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|

## <a name="remarks"></a>Note

Prima di .NET Framework 4, la Garbage Collection per workstation supportava la Garbage Collection in modalità simultanea, che eseguiva la Garbage Collection in background in un thread separato. A partire da .NET Framework 4, la Garbage Collection in modalità simultanea è stata sostituita dalla modalità in background, che esegue anch'essa la Garbage Collection in background in un thread separato. A partire da .NET Framework 4.5, l'operazione di Garbage Collection in background è disponibile anche per server. L' `<gcConcurrent>` elemento controlla se il runtime esegue una Garbage Collection simultanea o in background, se disponibile, o se esegue Garbage Collection in primo piano.

### <a name="to-disable-background-garbage-collection"></a>Per disabilitare lo sfondo Garbage Collection

> [!WARNING]
> A partire da .NET Framework 4, la Garbage Collection in modalità simultanea è sostituita dalla Garbage Collection in background. I termini *simultanei* e in *background* vengono usati in modo interscambiabile nella documentazione di .NET Framework. Per disabilitare il Garbage Collection in background, usare l'elemento `<gcConcurrent>`, come illustrato in questo articolo.

Per impostazione predefinita, il runtime usa la Garbage Collection in modalità simultanea che è ottimizzata per la latenza. Se si usa un'applicazione che prevede una notevole interazione da parte dell'utente, non disabilitare l'esecuzione simultanea di Garbage Collection in modo da ridurre il tempo di sospensione dell'applicazione durante l'esecuzione di Garbage Collection. Se si imposta l'attributo `enabled` dell'elemento `<gcConcurrent>` su `false`, da parte del runtime viene usata la Garbage Collection in modalità non simultanea, ottimizzata per la velocità effettiva. Il file di configurazione seguente disabilita la Garbage Collection in background.

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

 Se è presente un' `<gcConcurrentSetting>` impostazione nel file di configurazione del computer, definisce il valore predefinito per tutte le applicazioni .NET Framework. Con l'impostazione del file di configurazione del computer viene eseguito l'override dell'impostazione del file di configurazione dell'applicazione.

 Per altre informazioni sulle Garbage Collection simultanee e in background, vedere la sezione [Garbage Collection simultanea](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection) nell'articolo [nozioni fondamentali di Garbage Collection](../../../../standard/garbage-collection/fundamentals.md) .

## <a name="example"></a>Esempio

Nell'esempio seguente viene abilitata la Garbage Collection simultanea:

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
