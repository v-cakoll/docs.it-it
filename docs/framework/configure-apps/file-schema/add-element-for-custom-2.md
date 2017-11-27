---
title: '&lt;aggiungere&gt; elemento per NameValueSectionHandler e DictionarySectionHandler'
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e9dc671f0df9034410d20fdf69862884d6b3b300
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<aggiungere > elemento per NameValueSectionHandler e DictionarySectionHandler

Aggiunge le impostazioni dell'applicazione personalizzata. Ogni  **\<aggiungere >** tag contiene una coppia chiave/valore.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<sectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<Aggiungi >**

## <a name="syntax"></a>Sintassi

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a>Attributi

| Attributo | Descrizione |
| --------- | ----------- |
| **key**   | Attributo obbligatorio.<br><br>Specifica il nome dell'impostazione. |
| **value** | Attributo obbligatorio.<br><br>Specifica il valore dell'impostazione. |

## <a name="parent-element"></a>Elemento padre

| Elemento | Descrizione |
| ------- | ------------|
| [**\<sectionName >** elemento](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | Definisce le impostazioni per le sezioni di configurazione personalizzate che utilizzano il <xref:System.Configuration.NameValueSectionHandler> e <xref:System.Configuration.DictionarySectionHandler> classi. |

## <a name="child-elements"></a>Elementi figlio

Nessuno

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come definire una sezione di configurazione personalizzato e utilizzare il  **\<aggiungere >** elemento per inserire le impostazioni nella sezione:

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
</configuration>
```

## <a name="configuration-file"></a>File di configurazione

Questo elemento può essere usato nel file di configurazione dell'applicazione, i file di configurazione macchina (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedere anche

[Schema di file di configurazione per .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
