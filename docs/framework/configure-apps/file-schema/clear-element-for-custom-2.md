---
title: <clear>elemento per NameValueSectionHandler e DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: fbb689db4abc5d59729d9a4d9807a02a0983d40b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927702"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<Cancella > elemento per NameValueSectionHandler e DictionarySectionHandler

Cancella tutte le impostazioni definite in precedenza in una sezione.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp;[ **\<sectionName>** ](custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<clear>**

## <a name="syntax"></a>Sintassi

```xml
<clear />
```

## <a name="attributes"></a>Attributi

Nessuna

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ------------|
| [SectionName > elemento  **\<** ](custom-element-2.md) | Definisce le impostazioni per le sezioni di configurazione personalizzate <xref:System.Configuration.NameValueSectionHandler> che <xref:System.Configuration.DictionarySectionHandler> usano le classi e. |

## <a name="child-elements"></a>Elementi figlio

Nessuna

## <a name="remarks"></a>Note

È possibile utilizzare l'  **\<elemento clear >** per rimuovere tutte le impostazioni dall'applicazione definite a un livello superiore nella gerarchia dei file di configurazione.

## <a name="example"></a>Esempio

Questo esempio definisce un file di configurazione del computer e un file di configurazione dell'applicazione e Mostra come usare l'  **\<elemento clear >** in un file di configurazione dell'applicazione per cancellare le sezioni precedentemente definite nella configurazione del computer file.

Il seguente codice del file di configurazione del computer dichiara la sezione  **\<>** :

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

Il codice del file di configurazione dell'applicazione seguente consente di rimuovere tutte le impostazioni dalla  **\<sezione >** . L'applicazione non è in  **\<** grado di recuperare le impostazioni dichiarate nella sezione > della sezione del file di configurazione del computer.

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>File di configurazione

Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedere anche

- [Schema del file di configurazione per il .NET Framework](index.md)
