---
title: Elemento <Thread_UseAllCpuGroups>
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
ms.openlocfilehash: a3a612c0ffbcb211157b9623d298ce8ad7a13e94
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73115403"
---
# <a name="thread_useallcpugroups-element"></a>\<Thread_UseAllCpuGroups> Elemento

Specifica se il runtime distribuisce i thread gestiti tra tutti i gruppi di CPU.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Thread_UseAllCpuGroups>**  

## <a name="syntax"></a>Sintassi

```xml
<Thread_UseAllCpuGroups
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

|Attributo|Descrizione|
|---------------|-----------------|
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se il runtime distribuisce i thread gestiti tra tutti i gruppi di CPU.|

## <a name="enabled-attribute"></a>Attributo enabled

|Valore|Description|
|-----------|-----------------|
|`false`|Il runtime non distribuisce i thread gestiti tra più gruppi di CPU. Questo è il valore predefinito.|
|`true`|Il runtime distribuisce i thread gestiti tra più gruppi di CPU, se il computer dispone di più gruppi di CPU e l' [\<GCCpuGroup>](gccpugroup-element.md) elemento è abilitato.|

### <a name="child-elements"></a>Elementi figlio

No.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|

## <a name="remarks"></a>Commenti

Quando un computer dispone di più gruppi di CPU, l'abilitazione di questo elemento fa sì che il runtime distribuisca i thread gestiti in tutti i gruppi di CPU. Per usare questa funzionalità, è necessario abilitare anche l' [\<GCCpuGroup>](gccpugroup-element.md) elemento, che estende Garbage Collection a tutti i gruppi di CPU e prende in considerazione tutti i core quando crea e bilancia gli heap. L'abilitazione dell' [\<GCCpuGroup>](gccpugroup-element.md) elemento richiede l'abilitazione dell' [\<gcServer>](gcserver-element.md) elemento. Se questi elementi non sono abilitati, l'abilitazione dell' `<Thread_UseAllCpuGroups>` elemento non ha alcun effetto.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come abilitare il supporto per più gruppi di CPU.

```xml
<configuration>
   <runtime>
      <Thread_UseAllCpuGroups enabled="true"/>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Vedi anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema del file di configurazione](../index.md)
- [\<GCCpuGroup>Elemento](gccpugroup-element.md)
