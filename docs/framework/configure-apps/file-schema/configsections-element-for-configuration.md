---
title: Elemento <configSections> per <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 55116f1fe6fdffffea8f26d8a4de783c7305ada3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155349"
---
# <a name="configsections-element-for-configuration"></a>\<elemento di> \<configSections per la> di configurazione

Contiene le dichiarazioni della sezione di configurazione e dello spazio dei nomi.

[** \<>**](configuration-element.md) &nbsp; &nbsp;configurazione configSections>** \<**

## <a name="attributes"></a>Attributes

nessuno

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ----------- |
| [**\<>di configurazione**](configuration-element.md) | Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework. |

## <a name="child-elements"></a>Elementi figlio

|     | Descrizione |
| --- | ----------- |
| [**\<sezione>**](section-element.md) | Contiene una dichiarazione di sezione di configurazione. |
| [**\<>gruppo section**](sectiongroup-element-for-configsections.md) | Definisce uno spazio dei nomi per le sezioni di configurazione. |
| [**\<rimuovere>**](remove-element-for-configsections.md) | Rimuove una sezione o un gruppo di sezioni predefinito. |
| [**\<>chiari**](clear-element-for-configsections.md) | Cancella tutte le sezioni e i gruppi di sezioni definiti in precedenza. |

## <a name="remarks"></a>Osservazioni

Se questo elemento si trova in un file di configurazione, deve essere il primo elemento figlio dell'elemento ** \<>configurazione.**

## <a name="example"></a>Esempio

L'esempio seguente mostra come definire una sezione di configurazione e definire le impostazioni per tale sezione:The following example shows how to define a configuration section and define settings for that section:

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

Questo elemento può essere utilizzato nei file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine.config*) e nei file *Web.config* che non si trovano a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedere anche

- [Schema del file di configurazione per .NET Framework](index.md)
