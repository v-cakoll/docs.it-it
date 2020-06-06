---
title: Elemento <clear> per <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
ms.openlocfilehash: 66abd7f057bc6d060e50a889a945281d07c97592
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155427"
---
# <a name="clear-element-for-configsections"></a>Elemento \<clear> per \<configSections>

Cancella tutte le sezioni e i gruppi di sezioni definiti in precedenza.

[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) &nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a>Sintassi

```xml
<clear/>
```

## <a name="attribute"></a>Attributo

|           | Descrizione |
| --------- | ----------- |
| **nome**  | Attributo obbligatorio.<br><br>Specifica il nome della sezione o del gruppo di sezioni da rimuovere. |

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ----------- |
| [**\<configSections>** Elemento](configsections-element-for-configuration.md) | Contiene la sezione di configurazione e le dichiarazioni dello spazio dei nomi. |

## <a name="child-elements"></a>Elementi figlio

nessuno

## <a name="remarks"></a>Osservazioni

L' **\<clear>** elemento rimuove tutti i gruppi di sezioni e sezioni dall'applicazione definiti in precedenza nel file di configurazione corrente o a un livello superiore nella gerarchia dei file di configurazione.

## <a name="example"></a>Esempio

Questo esempio definisce un file di configurazione del computer e un file di configurazione dell'applicazione e Mostra come usare l' **\<clear>** elemento in un file di configurazione dell'applicazione per cancellare le sezioni definite in precedenza nel file di configurazione del computer.

Il seguente codice del file di configurazione del computer dichiara due sezioni, **\<sampleSection>** e **\<anotherSampleSection>** , che vengono lette prima del file di configurazione dell'applicazione:

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

Il codice del file di configurazione dell'applicazione seguente cancella tutte le sezioni precedentemente dichiarate. L'applicazione non può usare o recuperare le impostazioni in una delle sezioni dichiarate nel file di configurazione del computer. Tuttavia, può utilizzare le impostazioni da **\<anotherSection>** perché si trova dopo l' **\<clear>** elemento.

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

Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedi anche

- [Schema del file di configurazione per il .NET Framework](index.md)
