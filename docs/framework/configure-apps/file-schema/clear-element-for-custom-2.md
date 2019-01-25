---
title: '&lt;Cancella&gt; elemento per NameValueSectionHandler e DictionarySectionHandler'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 55925ee5e9c5a17f14bd199125dbaacbadb9d928
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720941"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<Cancella > elemento per NameValueSectionHandler e DictionarySectionHandler

Cancella tutte le impostazioni definite in precedenza in una sezione.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a>Sintassi

```xml
<clear />
```

## <a name="attributes"></a>Attributi

nessuno

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ------------|
| [**\<sectionName >** elemento](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | Definisce le impostazioni per le sezioni di configurazione personalizzati che usano il <xref:System.Configuration.NameValueSectionHandler> e <xref:System.Configuration.DictionarySectionHandler> classi. |

## <a name="child-elements"></a>Elementi figlio

nessuno

## <a name="remarks"></a>Note

È possibile usare la  **\<clear >** elemento da cui rimuovere tutte le impostazioni dall'applicazione che sono stati definiti a un livello superiore nella gerarchia di file di configurazione.

## <a name="example"></a>Esempio

In questo esempio definisce un file di configurazione di computer e un file di configurazione dell'applicazione e viene illustrato come utilizzare il  **\<clear >** elemento in un file di configurazione dell'applicazione per cancellare le sezioni definite in precedenza di file di configurazione macchina.

Il codice di file di configurazione macchina seguente dichiara la sezione  **\<mySection >**:

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

Il codice di file di configurazione dell'applicazione seguente rimuove tutte le impostazioni nelle  **\<mySection >**. L'applicazione non è possibile recuperare le impostazioni che sono state dichiarate nel nel  **\<mySection >** sezione del file di configurazione della macchina.

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>File di configurazione

Questo elemento può essere usato nel file di configurazione dell'applicazione, file di configurazione computer (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedere anche

- [Schema di file di configurazione per .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
