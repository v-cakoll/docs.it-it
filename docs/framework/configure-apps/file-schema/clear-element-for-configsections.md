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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155427"
---
# <a name="clear-element-for-configsections"></a>\<elemento> \<chiaro per la> configSections

Cancella tutte le sezioni e i gruppi di sezioni definiti in precedenza.

&nbsp; &nbsp; &nbsp; &nbsp; [** \<configurazione>configurazione**](configuration-element.md) &nbsp; **>>\<** [** \<**](configsections-element-for-configuration.md) &nbsp;

## <a name="syntax"></a>Sintassi

```xml
<clear/>
```

## <a name="attribute"></a>Attributo

|           | Descrizione |
| --------- | ----------- |
| **name**  | Attributo obbligatorio.<br><br>Specifica il nome della sezione o del gruppo di sezioni da rimuovere. |

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ----------- |
| [** \<configSections>** Elemento](configsections-element-for-configuration.md) | Contiene le dichiarazioni della sezione di configurazione e dello spazio dei nomi. |

## <a name="child-elements"></a>Elementi figlio

nessuno

## <a name="remarks"></a>Osservazioni

L'elemento ** \<clear>** rimuove tutte le sezioni e i gruppi di sezioni dall'applicazione definiti in precedenza nel file di configurazione corrente o a un livello superiore nella gerarchia dei file di configurazione.

## <a name="example"></a>Esempio

In questo esempio vengono definiti un file di configurazione del ** \<** computer e un file di configurazione dell'applicazione e viene illustrato come utilizzare l'elemento clear>in un file di configurazione dell'applicazione per cancellare le sezioni definite in precedenza nel file di configurazione del computer.

Il codice del file di configurazione del computer seguente dichiara due sezioni, ** \<sampleSection>** e ** \<anotherSampleSection>**, che vengono lette prima del file di configurazione dell'applicazione:

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

Il codice del file di configurazione dell'applicazione seguente cancella tutte le sezioni dichiarate in precedenza. L'applicazione non può utilizzare o recuperare le impostazioni in una delle sezioni dichiarate nel file di configurazione del computer. Tuttavia, è possibile utilizzare le impostazioni da ** \<un altroSezione>** perché viene dopo l'elemento ** \<di>chiaro.**

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

Questo elemento può essere utilizzato nei file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine.config*) e nei file *Web.config* che non si trovano a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedere anche

- [Schema del file di configurazione per .NET Framework](index.md)
