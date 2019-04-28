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
ms.openlocfilehash: 0e2be4d9384f1e1ef73ce6064184aa2621a517a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674103"
---
# <a name="gcconcurrent-element"></a>\<gcConcurrent > elemento

Specifica se in Common Language Runtime viene eseguita una procedura di Garbage Collection in un thread separato.

\<configuration>\
\<runtime>\
\<gcConcurrent>

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

## <a name="enabled-attribute"></a>attributo Enabled

|Value|Descrizione|
|-----------|-----------------|
|`false`|Non eseguire operazioni di garbage collection simultanea.|
|`true`|Viene eseguita la procedura di Garbage Collection in modo concorrente. Questa è l'impostazione predefinita.|

### <a name="child-elements"></a>Elementi figlio

Nessuno.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|

## <a name="remarks"></a>Note

Prima di .NET Framework 4, la Garbage Collection per workstation supportava la Garbage Collection in modalità simultanea, che eseguiva la Garbage Collection in background in un thread separato. A partire da .NET Framework 4, la Garbage Collection in modalità simultanea è stata sostituita dalla modalità in background, che esegue anch'essa la Garbage Collection in background in un thread separato. A partire da .NET Framework 4.5, l'operazione di Garbage Collection in background è disponibile anche per server. Il `<gcConcurrent>` elemento controlla se il runtime esegue entrambi simultanee o garbage collection in background, se disponibile, o se esegue la procedura di garbage collection in primo piano.

### <a name="to-disable-background-garbage-collection"></a>Per disabilitare la garbage collection in background

> [!WARNING]
> A partire da .NET Framework 4, la Garbage Collection in modalità simultanea è sostituita dalla Garbage Collection in background. I termini *simultanee* e *sfondo* vengono usati indifferentemente nella documentazione di .NET Framework. Per disabilitare il Garbage Collection in background, usare l'elemento `<gcConcurrent>`, come illustrato in questo articolo.

Per impostazione predefinita, il runtime usa la Garbage Collection in modalità simultanea che è ottimizzata per la latenza. Se si usa un'applicazione che prevede una notevole interazione da parte dell'utente, non disabilitare l'esecuzione simultanea di Garbage Collection in modo da ridurre il tempo di sospensione dell'applicazione durante l'esecuzione di Garbage Collection. Se si imposta l'attributo `enabled` dell'elemento `<gcConcurrent>` su `false`, da parte del runtime viene usata la Garbage Collection in modalità non simultanea, ottimizzata per la velocità effettiva. Il file di configurazione seguente disabilita la Garbage Collection in background.

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

 Se è presente un `<gcConcurrentSetting>` impostazione nel file di configurazione del computer, definisce il valore predefinito per tutte le applicazioni .NET Framework. Con l'impostazione del file di configurazione del computer viene eseguito l'override dell'impostazione del file di configurazione dell'applicazione.

 Per altre informazioni su simultanee e garbage collection in background, vedere la [garbage collection simultanea](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection) sezione il [principi fondamentali di Garbage Collection](../../../../standard/garbage-collection/fundamentals.md) articolo.

## <a name="example"></a>Esempio

L'esempio seguente Abilita garbage collection simultanea:

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
