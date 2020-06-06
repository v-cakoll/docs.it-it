---
title: Elemento GCLOHThreshold
ms.date: 11/20/2019
helpviewer_keywords:
- GCLOHThreshold element
- <GCLOHThreshold> element
ms.openlocfilehash: d72dc9d27984f60dfb6296217263ce8b176093c6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74451220"
---
# <a name="gclohthreshold-element"></a>Elemento GCLOHThreshold

Specifica la dimensione della soglia, in byte, che fa in modo che il Garbage Collector inserisca gli oggetti nell'heap degli oggetti grandi (LOH).

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold>

## <a name="syntax"></a>Sintassi

```xml
<GCLOHThreshold
   enabled="nnnn"/>
```

## <a name="attributes"></a>Attributi

|Attributo|Descrizione|
|---------------|-----------------|
|`enabled`|Attributo obbligatorio.<br /><br />Specifica le dimensioni della soglia che determinano l'uso degli oggetti nell'heap degli oggetti grandi.|

### <a name="enabled-attribute"></a>attributo enabled

|Valore|Description|
|-----------|-----------------|
|`nnnn`|Dimensione della soglia, in byte, che fa sì che gli oggetti vadano nell'heap degli oggetti grandi.|

## <a name="child-elements"></a>Elementi figlio

No.

## <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|

## <a name="remarks"></a>Commenti

Questa impostazione è stata introdotta in .NET Framework 4,8.

## <a name="see-also"></a>Vedi anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
- [Nozioni fondamentali di Garbage Collection](../../../../standard/garbage-collection/fundamentals.md)
- [Opzioni di configurazione della fase di esecuzione di NET Core per GC](../../../../core/run-time-config/garbage-collector.md)
