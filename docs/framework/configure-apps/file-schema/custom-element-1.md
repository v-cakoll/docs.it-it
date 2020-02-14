---
title: Elemento personalizzato per SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: 1d0431085a04d3fb817dfe0883779acc4d693084
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214795"
---
# <a name="custom-element-for-singletagsectionhandler"></a>Elemento personalizzato per SingleTagSectionHandler

Definisce le impostazioni in una sezione di configurazione personalizzata definita da una sezione \<> elemento e utilizza la classe <xref:System.Configuration.SingleTagSectionHandler>.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp; *\<sectionname >*

## <a name="syntax"></a>Sintassi

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a>Attributes

Attributi e valori di attributo sono definiti dall'utente.

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ----------- |
| [ **\<configuration>** ](configuration-element.md) | Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework. |

## <a name="child-elements"></a>Elementi figlio

nessuno

## <a name="remarks"></a>Osservazioni

L'elemento **\<sectionname >** è un elemento personalizzato definito da una [**sezione di\<>** ](section-element.md) tag nell'elemento\<[**configSections >** ](configsections-element-for-configuration.md) . Quando si chiama <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>, il sistema di configurazione restituisce un oggetto <xref:System.Collections.IDictionary>.

## <a name="example"></a>Esempio

Nell'esempio seguente viene dichiarato un elemento personalizzato denominato **\<sampleSection >** che contiene le impostazioni lette dalla classe <xref:System.Configuration.SingleTagSectionHandler>:

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
