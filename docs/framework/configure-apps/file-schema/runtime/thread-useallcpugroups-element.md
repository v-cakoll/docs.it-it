---
title: Elemento <Thread_UseAllCpuGroups>
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e9ee6bdb7094ea2bc9e283e331c0f6ad9b68e4f9
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663417"
---
# <a name="thread_useallcpugroups-element"></a>\<Elemento > Thread_UseAllCpuGroups

Specifica se il runtime distribuisce i thread gestiti tra tutti i gruppi di CPU.

\<> di configurazione \
\<> runtime \
\<Thread_UseAllCpuGroups>

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

|Valore|DESCRIZIONE|
|-----------|-----------------|
|`false`|Il runtime non distribuisce i thread gestiti tra più gruppi di CPU. Questa è l'impostazione predefinita.|
|`true`|Il runtime distribuisce i thread gestiti tra più gruppi di CPU, se il computer dispone di più gruppi di CPU e l' [ \<elemento > GCCpuGroup](gccpugroup-element.md) è abilitato.|

### <a name="child-elements"></a>Elementi figlio

Nessuno.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|

## <a name="remarks"></a>Note

Quando un computer dispone di più gruppi di CPU, l'abilitazione di questo elemento fa sì che il runtime distribuisca i thread gestiti in tutti i gruppi di CPU. Per usare questa funzionalità, è necessario abilitare anche l'elemento [ \<> GCCpuGroup](gccpugroup-element.md) , che estende Garbage Collection a tutti i gruppi di CPU e prende in considerazione tutti i core quando crea e bilancia gli heap. L'abilitazione dell' [ \<elemento > GCCpuGroup](gccpugroup-element.md) richiede l'abilitazione dell'elemento [ \<> di gcserver](gcserver-element.md) . Se questi elementi non sono abilitati, l' `<Thread_UseAllCpuGroups>` abilitazione dell'elemento non ha alcun effetto.

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

## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
- [\<Elemento > GCCpuGroup](gccpugroup-element.md)
