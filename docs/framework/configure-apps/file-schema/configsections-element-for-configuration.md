---
title: '&lt;configSections&gt; elemento per &lt;configurazione&gt;'
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7bcf425f345a3153a83cc60e76d87b3c32d83dbe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="configsections-element-for-configuration"></a>\<configSections > elemento per \<configurazione >

Contiene le dichiarazioni dello spazio dei nomi e di sezione di configurazione.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;**\<configSections >**

## <a name="attributes"></a>Attributi

Nessuno

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ----------- |
| [**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) | Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework. |

## <a name="child-elements"></a>Elementi figlio

|     | Descrizione |
| --- | ----------- |
| [**\<sezione >**](~/docs/framework/configure-apps/file-schema/section-element.md) | Contiene una dichiarazione di sezione di configurazione. |
| [**\<sectionGroup >**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | Definisce uno spazio dei nomi per le sezioni di configurazione. |
| [**\<remove>**](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) | Rimuove una sezione predefinita o il gruppo di sezione. |
| [**\<clear>**](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | Cancella tutte le sezioni definite in precedenza e i gruppi di sezioni. |

## <a name="remarks"></a>Note

Se questo elemento è incluso un file di configurazione, deve essere il primo elemento figlio del  **\<configurazione >** elemento.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come definire una sezione di configurazione e impostazioni per la sezione:

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

Questo elemento può essere usato nel file di configurazione dell'applicazione, i file di configurazione macchina (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedere anche

[Schema di file di configurazione per .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
