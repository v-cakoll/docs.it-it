---
title: Elemento personalizzato per SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: a40f35838655f6021af0b2e966335803ec8c16b4
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "80635391"
---
# <a name="custom-element-for-singletagsectionhandler"></a>Elemento personalizzato per SingleTagSectionHandler

Definisce le impostazioni in una sezione di configurazione personalizzata definita da un \<section> elemento e utilizza la <xref:System.Configuration.SingleTagSectionHandler> classe.

[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;*\<sectionName>*

## <a name="syntax"></a>Sintassi

```xml
<sectionName key="value" key2="value2" />
```

## <a name="attributes"></a>Attributi

Attributi e valori di attributo sono definiti dall'utente.

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework. |

## <a name="child-elements"></a>Elementi figlio

nessuno

## <a name="remarks"></a>Osservazioni

L' **\<sectionName>** elemento è un elemento personalizzato definito da un [**\<section>**](section-element.md) tag nell' [**\<configSections>**](configsections-element-for-configuration.md) elemento. Il sistema di configurazione restituisce un <xref:System.Collections.IDictionary> oggetto quando si chiama <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType> .

## <a name="example"></a>Esempio

Nell'esempio seguente viene dichiarato un elemento personalizzato denominato **\<sampleSection>** che contiene le impostazioni lette dalla <xref:System.Configuration.SingleTagSectionHandler> classe:

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

## <a name="see-also"></a>Vedi anche

- [Schema del file di configurazione per il .NET Framework](index.md)
