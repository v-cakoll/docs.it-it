---
title: <remove>elemento per NameValueSectionHandler e DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: cd338ff2d613be31ab1524f6baed6107f803a688
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920943"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<rimuovere > elemento per NameValueSectionHandler e DictionarySectionHandler

Rimuove un'impostazione definita in precedenza.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp;[ **\<sectionName>** ](custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<remove>**

## <a name="syntax"></a>Sintassi

```xml
<add remove="key" />
```

## <a name="attribute"></a>Attributo

|           | Descrizione |
| --------- | ----------- |
| **key**   | Attributo obbligatorio.<br><br>Specifica il nome dell'impostazione da rimuovere. |

## <a name="parent-element"></a>Elemento padre

| Elemento | Descrizione |
| ------- | ------------|
| [SectionName > elemento  **\<** ](custom-element-2.md) | Definisce le impostazioni per le sezioni di configurazione personalizzate <xref:System.Configuration.NameValueSectionHandler> che <xref:System.Configuration.DictionarySectionHandler> usano le classi e. |

## <a name="child-elements"></a>Elementi figlio

Nessuna

## <a name="remarks"></a>Note

È possibile usare l'  **\<elemento remove >** per rimuovere le impostazioni dall'applicazione definite a un livello superiore nella gerarchia dei file di configurazione.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come utilizzare l'  **\<elemento remove >** in un file di configurazione dell'applicazione per rimuovere le impostazioni definite in precedenza nel file di configurazione del computer.

Nel codice del file di configurazione del computer seguente `key1` viene dichiarata la sezione  **\<>** e vengono aggiunte `key2`due impostazioni:

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

Il codice del file di configurazione dell'applicazione `key2` seguente consente di rimuovere l'impostazione dall'  **\<area >** :

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>File di configurazione

Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedere anche

- [Schema del file di configurazione per il .NET Framework](index.md)
