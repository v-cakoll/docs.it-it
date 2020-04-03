---
title: Elemento personalizzato per SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: a40f35838655f6021af0b2e966335803ec8c16b4
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635391"
---
# <a name="custom-element-for-singletagsectionhandler"></a>Elemento personalizzato per SingleTagSectionHandler

Definisce le impostazioni in una sezione \<di configurazione personalizzata <xref:System.Configuration.SingleTagSectionHandler> definita da una sezione> elemento e utilizza la classe .

sezione &nbsp; &nbsp;>[** \<**](configuration-element.md) * \<configurazioneNome>*

## <a name="syntax"></a>Sintassi

```xml
<sectionName key="value" key2="value2" />
```

## <a name="attributes"></a>Attributi

Gli attributi e i valori degli attributi sono definiti dall'utente.

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ----------- |
| [**\<>di configurazione**](configuration-element.md) | Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework. |

## <a name="child-elements"></a>Elementi figlio

nessuno

## <a name="remarks"></a>Osservazioni

L'elemento ** \<>sectionName** è un [** \<**](section-element.md) elemento personalizzato definito da una sezione>tag nell'elemento [** \<>configSections.**](configsections-element-for-configuration.md) Il sistema di <xref:System.Collections.IDictionary> configurazione restituisce un oggetto quando si chiama <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.

## <a name="example"></a>Esempio

L'esempio seguente dichiara un elemento personalizzato denominato ** \<sampleSection>** che contiene le impostazioni lette dalla classe:The following example declares a custom element called sampleSection>that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:

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

Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine.config*) e nei file *Web.config* che non si trovano a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedere anche

- [Schema del file di configurazione per .NET Framework](index.md)
