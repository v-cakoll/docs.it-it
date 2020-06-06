---
title: <GCCpuGroup> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: f1cbe5a7109d6e4aae2e92710920a1c6b3a40d00
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "82102892"
---
# <a name="gccpugroup-element"></a>\<GCCpuGroup> Elemento

Specifica se Garbage Collection supporta più gruppi di CPU.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**

## <a name="syntax"></a>Sintassi

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

|Attributo|Descrizione|
|---------------|-----------------|
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se Garbage Collection supporta più gruppi di CPU.|

## <a name="enabled-attribute"></a>Attributo enabled

|Valore|Description|
|-----------|-----------------|
|`false`|Garbage Collection non supporta più gruppi di CPU. Questo è il valore predefinito.|
|`true`|Se il server Garbage Collection è abilitato, Garbage Collection supporta più gruppi di CPU.|

### <a name="child-elements"></a>Elementi figlio

No.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|

## <a name="remarks"></a>Commenti

Quando un computer dispone di più gruppi di CPU e il Garbage Collection server è abilitato (vedere l' [\<gcServer>](gcserver-element.md) elemento), l'abilitazione di questo elemento estende Garbage Collection in tutti i gruppi di CPU e prende in considerazione tutti i core quando crea e bilancia gli heap.

> [!NOTE]
> Questo elemento si applica solo ai thread Garbage Collection. Per consentire al runtime di distribuire i thread utente in tutti i gruppi di CPU, è necessario abilitare anche l' [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) elemento.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come abilitare Garbage Collection per più gruppi di CPU.

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Vedi anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema del file di configurazione](../index.md)
- [Disabilitare Garbage Collection simultanee](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [Operazione di Garbage Collection per workstation e server](../../../../standard/garbage-collection/workstation-server-gc.md)
