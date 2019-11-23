---
title: Elemento <configSections> per <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6024144b6f12df22369366f04c3cbad02c5011d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119024"
---
# <a name="configsections-element-for-configuration"></a>\<elemento > configSections per \<Configuration >

Contiene la sezione di configurazione e le dichiarazioni dello spazio dei nomi.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp; **\<configSections>**

## <a name="attributes"></a>Attributi

None

## <a name="parent-element"></a>Elemento padre

|     | description |
| --- | ----------- |
| [ **\<configuration>** ](configuration-element.md) | Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework. |

## <a name="child-elements"></a>Elemento figlio

|     | description |
| --- | ----------- |
| [ **\<sezione >** ](section-element.md) | Contiene una dichiarazione della sezione di configurazione. |
| [ **\<sectionGroup>** ](sectiongroup-element-for-configsections.md) | Definisce uno spazio dei nomi per le sezioni di configurazione. |
| [ **\<remove>** ](remove-element-for-configsections.md) | Rimuove una sezione o un gruppo di sezioni predefinito. |
| [ **\<clear>** ](clear-element-for-configsections.md) | Cancella tutte le sezioni e i gruppi di sezioni definiti in precedenza. |

## <a name="remarks"></a>Osservazioni

Se questo elemento si trova in un file di configurazione, deve essere il primo elemento figlio dell'elemento **\<configuration >** .

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come definire una sezione di configurazione e definire le impostazioni per la sezione:

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a>File di configurazione

Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedere anche

- [Schema del file di configurazione per il .NET Framework](index.md)
