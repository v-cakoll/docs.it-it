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
ms.openlocfilehash: 249518ae7477d284d50f9010757db83b7752c657
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102918"
---
# <a name="gcconcurrent-element"></a>\<elemento> gcConcurrent

Specifica se in Common Language Runtime viene eseguita una procedura di Garbage Collection in un thread separato.

[\<>di configurazione](../configuration-element.md)\
&nbsp;&nbsp;[\<>di runtime](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<> di gcConcurrent

## <a name="syntax"></a>Sintassi

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributes

|Attributo|Descrizione|
|---------------|-----------------|
|`enabled`|Attributo obbligatorio.<br /><br />Specifica se il runtime esegue operazioni di Garbage Collection simultaneamente.|

#### <a name="enabled-attribute"></a>attributo enabled

|valore|Descrizione|
|-----------|-----------------|
|`false`|Non esegue la procedura di Garbage Collection contemporaneamente.|
|`true`|Viene eseguita la procedura di Garbage Collection in modo concorrente. Questa è la modalità predefinita.|

### <a name="child-elements"></a>Elementi figlio

No.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|

## <a name="remarks"></a>Osservazioni

Prima di .NET Framework 4, l'operazione di Garbage Collection per workstation supportava l'operazione di Garbage Collection simultanea, che eseguiva operazioni di Garbage Collection in background in un thread separato. In .NET Framework 4.NET Framework 4, la Garbage Collection simultanea è stata sostituita da GC in background, che esegue anche la garbage collection in background in un thread separato. A partire da .NET Framework 4.5.NET Framework 4.5,NET Framework 4.5, la raccolta in background è diventata disponibile nell'operazione di Garbage Collection per server. L'elemento **gcConcurrent** controlla se il runtime esegue un'operazione di Garbage Collection simultanea o in background, se disponibile o se esegue operazioni di Garbage Collection in primo piano.

### <a name="to-disable-background-garbage-collection"></a>Per disabilitare l'operazione di Garbage Collection in background

> [!WARNING]
> A partire da .NET Framework 4.NET Framework 4, l'operazione di Garbage Collection simultanea viene sostituita da Garbage Collection in background. I termini *simultanei* e *in background* vengono utilizzati in modo intercambiabile nella documentazione di .NET Framework. Per disabilitare l'operazione di Garbage Collection in background, usare l'elemento **gcConcurrent,** come descritto in questo articolo.

Per impostazione predefinita, il runtime usa la Garbage Collection in modalità simultanea che è ottimizzata per la latenza. Se si usa un'applicazione che prevede una notevole interazione da parte dell'utente, non disabilitare l'esecuzione simultanea di Garbage Collection in modo da ridurre il tempo di sospensione dell'applicazione durante l'esecuzione di Garbage Collection. Se si `enabled` imposta l'attributo dell'elemento **gcConcurrent** su `false`, il runtime utilizza un'operazione di Garbage Collection non simultanea, ottimizzata per la velocità effettiva.

Il file di configurazione seguente disabilita l'operazione di Garbage Collection in background:The following configuration file disables background garbage collection:

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

Se è presente **un'impostazione gcConcurrentSetting** nel file di configurazione del computer, definisce il valore predefinito per tutte le applicazioni .NET Framework. Con l'impostazione del file di configurazione del computer viene eseguito l'override dell'impostazione del file di configurazione dell'applicazione.

Per ulteriori informazioni sull'operazione di Garbage Collection simultanea e in background, vedere [Garbage Collection](../../../../standard/garbage-collection/background-gc.md)in background .

## <a name="example"></a>Esempio

L'esempio seguente abilita l'operazione di Garbage Collection in background:The following example enables background garbage collection:

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema del file di configurazione](../index.md)
- [Nozioni fondamentali di Garbage Collection](../../../../standard/garbage-collection/fundamentals.md)
