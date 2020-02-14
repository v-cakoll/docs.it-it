---
title: Elemento personalizzato per NameValueSectionHandler e DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
ms.openlocfilehash: e5c5c6cf5744aa385e6f6700cad623751a4d7427
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215484"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>Elemento personalizzato per NameValueSectionHandler e DictionarySectionHandler

Definisce le impostazioni per le sezioni di configurazione personalizzate che usano le classi <xref:System.Configuration.NameValueSectionHandler> e <xref:System.Configuration.DictionarySectionHandler>.

[ **\<configuration>** ](configuration-element.md)\
&nbsp;&nbsp; **\<sectionname >**

## <a name="attributes"></a>Attributes

nessuno

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ----------- |
| [ **\<configuration>** ](configuration-element.md) | Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework. |

## <a name="child-elements"></a>Elementi figlio

|     | Descrizione |
| --- | ----------- |
| [ **\<aggiungere >** ](add-element-for-custom-2.md) per <xref:System.Configuration.NameValueSectionHandler> e <xref:System.Configuration.DictionarySectionHandler>  | Aggiunge le impostazioni dell'applicazione personalizzata. |
| [ **\<rimuovere >** ](remove-element-for-custom-2.md) per <xref:System.Configuration.NameValueSectionHandler> e <xref:System.Configuration.DictionarySectionHandler> | Rimuove un'impostazione definita in precedenza. |
| [ **\<deselezionare >** ](clear-element-for-custom-2.md) per <xref:System.Configuration.NameValueSectionHandler> e <xref:System.Configuration.DictionarySectionHandler> | Cancella tutte le impostazioni definite in precedenza in una sezione. |

## <a name="remarks"></a>Osservazioni

L'elemento **\<sectionname >** è un elemento personalizzato definito da una **sezione di\<>** tag nell'elemento\<**configSections >** .

La tabella seguente illustra il tipo di oggetto restituito dal metodo ConfigurationSettings. GetConfig per ogni gestore della sezione di configurazione:

| Gestore della sezione di configurazione                        | Tipo restituito                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come dichiarare sezioni che utilizzano le classi <xref:System.Configuration.DictionarySectionHandler> e <xref:System.Configuration.NameValueSectionHandler>.

Il primo elemento personalizzato è **\<> dictionarySample**, che contiene le impostazioni lette dalla classe <xref:System.Configuration.DictionarySectionHandler> nell'assembly `System.dll`. Il secondo elemento personalizzato è **\<sezione >** , che contiene le impostazioni lette dalla classe <xref:System.Configuration.NameValueSectionHandler> nell'assembly `System.dll`.

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
