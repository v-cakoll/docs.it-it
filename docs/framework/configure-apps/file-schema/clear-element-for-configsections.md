---
title: Elemento <clear> per <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
author: guardrex
ms.author: mairaw
ms.openlocfilehash: d824ae828dd025f3292990facaa5e423add9c282
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705350"
---
# <a name="clear-element-for-configsections"></a>\<Cancella > (elemento) per \<configSections >

Cancella tutte le sezioni definite in precedenza e i gruppi.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a>Sintassi

```xml
<clear/>
```

## <a name="attribute"></a>Attributo

|           | Descrizione |
| --------- | ----------- |
| **name**  | Attributo obbligatorio.<br><br>Specifica il nome della sezione o il gruppo di sezioni da rimuovere. |

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ----------- |
| [**\<configSections >** elemento](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | Contiene le dichiarazioni dello spazio dei nomi e sezione di configurazione. |

## <a name="child-elements"></a>Elementi figlio

nessuno

## <a name="remarks"></a>Note

Il  **\<clear >** elemento rimuove tutte le sezioni e gruppi dall'applicazione che sono state definite in precedenza nel file di configurazione corrente o a un livello superiore nella gerarchia di file di configurazione.

## <a name="example"></a>Esempio

In questo esempio definisce un file di configurazione di computer e un file di configurazione dell'applicazione e viene illustrato come utilizzare il  **\<clear >** elemento in un file di configurazione dell'applicazione per cancellare le sezioni definite in precedenza di file di configurazione macchina.

Il codice di file di configurazione macchina seguente dichiara due sezioni  **\<sampleSection >** e  **\<anotherSampleSection >**, che vengono lette prima che l'applicazione file di configurazione:

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

Il codice di file di configurazione dell'applicazione seguente cancella tutte le sezioni dichiarate in precedenza. L'applicazione non è possibile usare o recuperare le impostazioni in una delle sezioni che sono state dichiarate nel file di configurazione del computer. Tuttavia, può usare le impostazioni dal  **\<tale sezione si trova >** perché segue il  **\<deselezionare >** elemento.

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

Questo elemento può essere usato nel file di configurazione dell'applicazione, file di configurazione computer (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedere anche

- [Schema di file di configurazione per .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
