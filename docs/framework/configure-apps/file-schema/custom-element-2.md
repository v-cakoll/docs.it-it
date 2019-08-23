---
title: Elemento personalizzato per NameValueSectionHandler e DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 890269857aaa00ce62195ccb2f4cb184b363b61e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921024"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>Elemento personalizzato per NameValueSectionHandler e DictionarySectionHandler

Definisce le impostazioni per le sezioni di configurazione personalizzate <xref:System.Configuration.NameValueSectionHandler> che <xref:System.Configuration.DictionarySectionHandler> usano le classi e.

[ **\<configuration>** ](configuration-element.md)\
&nbsp;&nbsp; **\<sectionName>**

## <a name="attributes"></a>Attributi

Nessuna

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ----------- |
| [ **\<configuration>** ](configuration-element.md) | Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework. |

## <a name="child-elements"></a>Elementi figlio

|     | Descrizione |
| --- | ----------- |
| aggiungere > per e [ **\<** ](add-element-for-custom-2.md) <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler>  | Aggiunge le impostazioni dell'applicazione personalizzata. |
| rimuovere > per e [ **\<** ](remove-element-for-custom-2.md) <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler> | Rimuove un'impostazione definita in precedenza. |
| Cancella > per e [ **\<** ](clear-element-for-custom-2.md) <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler> | Cancella tutte le impostazioni definite in precedenza in una sezione. |

## <a name="remarks"></a>Note

**L'\<elemento sectionName >** è un elemento personalizzato definito da una  **\<sezione >** tag nell'  **\<elemento > configSections** .

La tabella seguente illustra il tipo di oggetto restituito dal metodo ConfigurationSettings. GetConfig per ogni gestore della sezione di configurazione:

| Gestore della sezione di configurazione                        | Tipo restituito                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come dichiarare sezioni che utilizzano le <xref:System.Configuration.DictionarySectionHandler> classi <xref:System.Configuration.NameValueSectionHandler> e.

Il primo elemento personalizzato è  **\<dictionarySample >** , che contiene <xref:System.Configuration.DictionarySectionHandler> le impostazioni lette dalla classe nell' `System.dll` assembly. Il secondo elemento personalizzato è  **\<section >** , che contiene <xref:System.Configuration.NameValueSectionHandler> le impostazioni lette dalla classe nell' `System.dll` assembly.

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
    <sectionGroup name="mySectionGroup">
      <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a>File di configurazione

Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedere anche

- [Schema del file di configurazione per il .NET Framework](index.md)
