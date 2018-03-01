---
title: '&lt;deselezionare&gt; elemento per &lt;configSections&gt;'
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e48887cf7e227f463b92edd50f69746bbd8abd0a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="clear-element-for-configsections"></a>\<Deselezionare > elemento per \<configSections >

Cancella tutte le sezioni definite in precedenza e i gruppi di sezioni.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<Deselezionare >**

## <a name="syntax"></a>Sintassi

```xml
<clear/>
```

## <a name="attribute"></a>Attributo

|           | Descrizione |
| --------- | ----------- |
| **name**  | Attributo obbligatorio.<br><br>Specifica il nome della sezione o del gruppo di sezione da rimuovere. |

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ----------- |
| [**\<configSections >** elemento](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | Contiene le dichiarazioni dello spazio dei nomi e di sezione di configurazione. |

# <a name="child-elements"></a>Elementi figlio

nessuno

## <a name="remarks"></a>Note

Il  **\<deselezionare >** elemento rimuove tutte le sezioni e gruppi dall'applicazione che sono state definite nel file di configurazione corrente o a un livello superiore nella gerarchia di file di configurazione.

## <a name="example"></a>Esempio

In questo esempio definisce un file di configurazione del computer e un file di configurazione dell'applicazione e viene illustrato come utilizzare il  **\<deselezionare >** elemento in un file di configurazione dell'applicazione per cancellare le sezioni definite in precedenza di file di configurazione di computer.

Nel seguente codice di file di configurazione di computer vengono dichiarate due sezioni,  **\<sampleSection >** e  **\<anotherSampleSection >**, che vengono lette prima che l'applicazione file di configurazione:

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
    <section name="anotherSampleSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

Il seguente codice di file di configurazione dell'applicazione Cancella tutte le sezioni dichiarate in precedenza. L'applicazione non è possibile utilizzare o recuperare le impostazioni in una delle sezioni che sono state dichiarate nel file di configurazione del computer. Tuttavia, è possibile utilizzare le impostazioni di  **\<tale sezione si trova >** perché proviene dopo il  **\<deselezionare >** elemento.

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <clear/>
    <section name="anotherSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <anotherSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a>File di configurazione

Questo elemento può essere usato nel file di configurazione dell'applicazione, i file di configurazione macchina (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedere anche

[Schema di file di configurazione per .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
