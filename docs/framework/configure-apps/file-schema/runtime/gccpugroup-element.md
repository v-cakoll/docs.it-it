---
title: <GCCpuGroup> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: f1cbe5a7109d6e4aae2e92710920a1c6b3a40d00
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102892"
---
# <a name="gccpugroup-element"></a>\<Elemento> GCCpuGroup

Specifica se Garbage Collection supporta più gruppi di CPU.

[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>di runtime**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<>di GCCpuGroup**

## <a name="syntax"></a>Sintassi

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributes

|Attributo|Descrizione|
|---------------|-----------------|
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se Garbage Collection supporta più gruppi di CPU.|

## <a name="enabled-attribute"></a>Attributo enabled

|valore|Descrizione|
|-----------|-----------------|
|`false`|La procedura di Garbage Collection non supporta più gruppi di CPU. Questa è la modalità predefinita.|
|`true`|La Garbage Collection supporta più gruppi di CPU, se l'operazione di Garbage Collection per server è abilitata.|

### <a name="child-elements"></a>Elementi figlio

No.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|

## <a name="remarks"></a>Osservazioni

Quando un computer dispone di più gruppi di CPU e la Garbage Collection del server è abilitata (vedere l'elemento [ \<gallida>),](gcserver-element.md) l'abilitazione di questo elemento estende l'operazione di Garbage Collection in tutti i gruppi di CPU e tiene conto di tutti i core durante la creazione e il bilanciamento degli heap.

> [!NOTE]
> Questo elemento si applica solo ai thread di Garbage Collection.This element applies only to garbage collection threads. Per consentire al runtime di distribuire i thread utente tra tutti i gruppi di CPU, è necessario abilitare anche l'elemento [ \<>Thread_UseAllCpuGroups.](thread-useallcpugroups-element.md)

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come abilitare la procedura di Garbage Collection per più gruppi di CPU.

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema del file di configurazione](../index.md)
- [Disabilitare Garbage Collection simultanea](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [Operazione di Garbage Collection per workstation e server](../../../../standard/garbage-collection/workstation-server-gc.md)
