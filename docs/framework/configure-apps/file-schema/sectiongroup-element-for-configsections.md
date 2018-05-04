---
title: '&lt;sectionGroup&gt; elemento per &lt;configSections&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
author: guardrex
ms.author: mairaw
ms.openlocfilehash: b898c81700e95ec9bc94e04c5a76494b7ac4b0dc
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="sectiongroup-element-for-configsections"></a>\<sectionGroup > elemento per \<configSections >

Definisce uno spazio dei nomi per le sezioni di configurazione.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup >**

## <a name="syntax"></a>Sintassi

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a>Attributo

|           | Descrizione |
| --------- | ----------- |
| **name**  | Attributo obbligatorio.<br><br>Specifica il nome del gruppo di sezioni a cui che si sta definendo. |

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ----------- |
| [**\<configSections >** elemento](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | Contiene le dichiarazioni dello spazio dei nomi e di sezione di configurazione. |

## <a name="child-elements"></a>Elementi figlio

|     | Descrizione |
| --- | ----------- |
| [**\<sezione >**](~/docs/framework/configure-apps/file-schema/section-element.md) | Contiene una dichiarazione di sezione di configurazione. |

## <a name="remarks"></a>Note

La dichiarazione di un gruppo di sezioni, crea un tag di contenitore per le sezioni di configurazione e assicura che non sono presenti conflitti di denominazione con sezioni di configurazione definite da un altro utente. È possibile annidare  **\<sectionGroup >** elementi all'interno di altro.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come dichiarare un gruppo di sezioni e dichiarare sezioni all'interno di un gruppo di sezioni:

```xml
<configuration>
  <configSections>
    <sectionGroup name="mySectionGroup">
      <section name="mySection"
               type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a>File di configurazione

Questo elemento può essere usato nel file di configurazione dell'applicazione, i file di configurazione macchina (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedere anche

[Schema di file di configurazione per .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
