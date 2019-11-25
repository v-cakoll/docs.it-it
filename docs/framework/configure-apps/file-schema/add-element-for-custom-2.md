---
title: elemento <add> per NameValueSectionHandler e DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ac07fc9ba6f030209a5e0d0160689fab95bc1b4a
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088756"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<aggiungere > elemento per NameValueSectionHandler e DictionarySectionHandler

Aggiunge le impostazioni dell'applicazione personalizzata. Ogni **\<Aggiungi tag >** contiene una coppia chiave/valore.

[ **\<configuration>** ](configuration-element.md)\
&nbsp;&nbsp;[ **\<sectionname >** ](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<aggiungi >**

## <a name="syntax"></a>Sintassi

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a>Attributi

| Attributo | Descrizione |
| --------- | ----------- |
| **key**   | Attributo obbligatorio.<br><br>Specifica il nome dell'impostazione. |
| **valore** | Attributo obbligatorio.<br><br>Specifica il valore dell'impostazione. |

## <a name="parent-element"></a>Elemento padre

| Elemento | Descrizione |
| ------- | ------------|
| [ **\<sectionname >** Elemento](custom-element-2.md) | Definisce le impostazioni per le sezioni di configurazione personalizzate che usano le classi <xref:System.Configuration.NameValueSectionHandler> e <xref:System.Configuration.DictionarySectionHandler>. |

## <a name="child-elements"></a>Elementi figlio

Nessuno

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come definire una sezione di configurazione personalizzata e utilizzare l'elemento **\<aggiungi >** per inserire le impostazioni nella sezione:

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

Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedere anche

- [Schema del file di configurazione per il .NET Framework](index.md)
