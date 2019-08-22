---
title: <GCCpuGroup> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 197ab9dbc1ec85bf8961f60bb26496eab788e63f
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663694"
---
# <a name="gccpugroup-element"></a>\<Elemento > GCCpuGroup

Specifica se Garbage Collection supporta più gruppi di CPU.

\<> di configurazione \
\<> runtime \
\<GCCpuGroup>

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

|Valore|DESCRIZIONE|
|-----------|-----------------|
|`false`|Garbage Collection non supporta più gruppi di CPU. Questa è l'impostazione predefinita.|
|`true`|Se il server Garbage Collection è abilitato, Garbage Collection supporta più gruppi di CPU.|

### <a name="child-elements"></a>Elementi figlio

Nessuno.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|

## <a name="remarks"></a>Note

Quando un computer dispone di più gruppi di CPU e Garbage Collection server è abilitato (vedere l' [ \<elemento > gcserver](gcserver-element.md) ), l'abilitazione di questo elemento estende Garbage Collection in tutti i gruppi di CPU e prende in considerazione tutti i core durante la creazione e heap di bilanciamento.

> [!NOTE]
> Questo elemento si applica solo ai thread Garbage Collection. Per consentire al runtime di distribuire i thread utente in tutti i gruppi di CPU, è necessario abilitare anche l' [ \<elemento Thread_UseAllCpuGroups >](thread-useallcpugroups-element.md) .

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

## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
- [Per disabilitare Garbage Collection simultanee](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [Operazione di Garbage Collection per workstation e server](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
