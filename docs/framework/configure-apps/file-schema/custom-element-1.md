---
title: Elemento personalizzato per SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 8fae3673fe72d036802cb1a8366aaa2430c38884
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927494"
---
# <a name="custom-element-for-singletagsectionhandler"></a>Elemento personalizzato per SingleTagSectionHandler

Definisce le impostazioni in una sezione di configurazione personalizzata definita da una \<sezione > elemento e utilizza la <xref:System.Configuration.SingleTagSectionHandler> classe.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp; *\<sectionName>*

## <a name="syntax"></a>Sintassi

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a>Attributi

Attributi e valori di attributo sono definiti dall'utente.

## <a name="parent-element"></a>Elemento padre

|     | DESCRIZIONE |
| --- | ----------- |
| [ **\<configuration>** ](configuration-element.md) | Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework. |

## <a name="child-elements"></a>Elementi figlio

Nessuna

## <a name="remarks"></a>Note

**L'\<elemento sectionName >** è un elemento personalizzato definito da una [ **\<sezione >** ](section-element.md) tag nell' [ **\<elemento > configSections**](configsections-element-for-configuration.md) . Il sistema di configurazione restituisce <xref:System.Collections.IDictionary> un oggetto quando si <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>chiama.

## <a name="example"></a>Esempio

Nell'esempio seguente viene dichiarato un elemento personalizzato denominato  **\<sampleSection >** che contiene <xref:System.Configuration.SingleTagSectionHandler> le impostazioni lette dalla classe:

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
