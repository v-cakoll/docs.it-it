---
title: <section> element
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
ms.openlocfilehash: 88f74c02ef627e9136e4437ffa150c36445266a3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153730"
---
# <a name="section-element"></a>Elemento \<section>

Contiene una dichiarazione della sezione di configurazione.

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**

## <a name="syntax"></a>Sintassi

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication"
         allowLocation="true|false" />
```

## <a name="required-attributes"></a>Attributi richiesti

|           | Descrizione |
| --------- | ----------- |
| **nome**  | Specifica il nome della sezione di configurazione. |
| **type**  | Specifica il nome della classe del gestore della sezione di configurazione che legge la sezione dal file di configurazione. Il valore del tipo ha la sintassi "Fully-Qualified-section-handler-Class-Name, Simple-assembly-name". Il nome dell'assembly semplice è il nome del file radice senza l'estensione *dll* . |

## <a name="optional-attributes"></a>Attributi facoltativi

Gli attributi seguenti sono applicabili solo per le applicazioni ASP.NET. Il sistema di configurazione Ignora questi attributi per altri tipi di applicazioni.

|                     | Descrizione |
| ------------------- | ----------- |
| **allowDefinition** | Specifica il file di configurazione in cui è possibile utilizzare la sezione. Usare uno dei valori seguenti:<br><br>**Ovunque**<br>Consente di utilizzare la sezione in qualsiasi file di configurazione. Questo è il valore predefinito.<br>**MachineOnly**<br>Consente di utilizzare la sezione solo nel file di configurazione del computer (*Machine. config*).<br>**MachineToApplication**<br>Consente di utilizzare la sezione nel file di configurazione del computer o nel file di configurazione dell'applicazione. |
| **allowLocation**   | Determina se la sezione può essere utilizzata all'interno dell' **\<location>** elemento. Usare uno dei valori seguenti:<br><br>**true**<br>Consente di utilizzare la sezione all'interno dell' **\<location>** elemento. Questo è il valore predefinito.<br>**false**<br>Non consente l'utilizzo della sezione all'interno dell' **\<location>** elemento. |

## <a name="parent-elements"></a>Elementi padre

|     | Descrizione |
| --- | ----------- |
| [**\<configSections>** Elemento](configsections-element-for-configuration.md) | Contiene la sezione di configurazione e le dichiarazioni dello spazio dei nomi. |
| [**\<sectionGroup>** Elemento](sectiongroup-element-for-configsections.md) | Definisce uno spazio dei nomi per le sezioni di configurazione. |

> [!NOTE]
> Un **\<section>** elemento è un elemento figlio di uno **\<configSections>** o **\<sectionGroup>** ma non entrambi.

## <a name="child-elements"></a>Elementi figlio

nessuno

## <a name="remarks"></a>Osservazioni

La dichiarazione di una sezione di configurazione definisce essenzialmente un nuovo elemento per il file di configurazione. Il nuovo elemento contiene impostazioni lette da un gestore della sezione di configurazione, ovvero una classe che implementa l' <xref:System.Configuration.IConfigurationSectionHandler> interfaccia. Gli attributi e gli elementi figlio di una sezione definita dipendono dal gestore della sezione usato per leggere le impostazioni.

La dichiarazione di un gestore della sezione di configurazione nel file *Machine. config* consente di usare la sezione di configurazione in qualsiasi file di configurazione dell'applicazione nel computer, a meno che l'attributo **allowDefinition** non specifichi diversamente.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come definire una sezione di configurazione e definire le impostazioni per la sezione:

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler"
             allowLocation="false" />
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
