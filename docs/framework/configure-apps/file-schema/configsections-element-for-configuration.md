---
title: Elemento <configSections> per <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: d522d004630dee942e24c39a936feae7dc957bd5
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300783"
---
# <a name="configsections-element-for-configuration"></a>\<configSections > (elemento) per \<configuration >

Contiene le dichiarazioni dello spazio dei nomi e sezione di configurazione.

[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp; **\<configSections>**

## <a name="attributes"></a>Attributi

nessuno

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ----------- |
| [ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) | Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework. |

## <a name="child-elements"></a>Elementi figlio

|     | Descrizione |
| --- | ----------- |
| [ **\<sezione >** ](~/docs/framework/configure-apps/file-schema/section-element.md) | Contiene una dichiarazione della sezione di configurazione. |
| [ **\<sectionGroup>** ](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | Definisce uno spazio dei nomi per le sezioni di configurazione. |
| [ **\<remove>** ](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) | Rimuove una sezione predefiniti o un gruppo di sezioni. |
| [ **\<clear>** ](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | Cancella tutte le sezioni definite in precedenza e i gruppi. |

## <a name="remarks"></a>Note

Se questo elemento è in un file di configurazione, deve essere il primo elemento figlio del  **\<configuration >** elemento.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come definire una sezione di configurazione e definire le impostazioni per tale sezione:

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

Questo elemento può essere usato nel file di configurazione dell'applicazione, file di configurazione computer (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedere anche

- [Schema di file di configurazione per .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
