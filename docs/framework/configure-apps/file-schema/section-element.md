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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153730"
---
# <a name="section-element"></a>\<sezione> elemento

Contiene una dichiarazione di sezione di configurazione.

[**\<>di configurazione**](configuration-element.md)\
&nbsp;&nbsp;[**\<>configSections**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<sezione>**

[**\<>di configurazione**](configuration-element.md)\
&nbsp;&nbsp;[**\<>configSections**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<>gruppo section**](sectiongroup-element-for-configsections.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sezione>**

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
| **name**  | Specifica il nome della sezione di configurazione. |
| **type**  | Specifica il nome della classe del gestore della sezione di configurazione che legge la sezione dal file di configurazione. Il valore del tipo ha la sintassi "fully-qualified-section-handler-class-name, simple-assembly-name". Il nome dell'assembly semplice è il nome del file radice senza l'estensione del file *DLL.* |

## <a name="optional-attributes"></a>Attributi facoltativi

Gli attributi seguenti sono applicabili solo per le applicazioni ASP.NET. Il sistema di configurazione ignora questi attributi per altri tipi di applicazione.

|                     | Descrizione |
| ------------------- | ----------- |
| **Allowdefinition** | Specifica in quale file di configurazione è possibile utilizzare la sezione. Usare uno dei valori seguenti:<br><br>**Ovunque**<br>Consente di utilizzare la sezione in qualsiasi file di configurazione. Questa è la modalità predefinita.<br>**Solo computer**<br>Consente di utilizzare la sezione solo nel file di configurazione del computer (*Machine.config*).<br>**MachineToApplication (Applicazione macchina)**<br>Consente di utilizzare la sezione nel file di configurazione del computer o nel file di configurazione dell'applicazione. |
| **allowLocation**   | Determina se la sezione può essere utilizzata all'interno dell'elemento ** \<>posizione.** Usare uno dei valori seguenti:<br><br>**true**<br>Consente di utilizzare la sezione all'interno dell'elemento ** \<location>.** Questa è la modalità predefinita.<br>**false**<br>Non consente l'utilizzo della sezione all'interno dell'elemento ** \<location>.** |

## <a name="parent-elements"></a>Elementi padre

|     | Descrizione |
| --- | ----------- |
| [** \<configSections>** Elemento](configsections-element-for-configuration.md) | Contiene le dichiarazioni della sezione di configurazione e dello spazio dei nomi. |
| [** \<sezione>gruppo** Elemento](sectiongroup-element-for-configsections.md) | Definisce uno spazio dei nomi per le sezioni di configurazione. |

> [!NOTE]
> Un ** \<** elemento>di sezione è un elemento figlio di ** \<configSections>** o ** \<sectionGroup>** ma non entrambi.

## <a name="child-elements"></a>Elementi figlio

nessuno

## <a name="remarks"></a>Osservazioni

La dichiarazione di una sezione di configurazione definisce essenzialmente un nuovo elemento per il file di configurazione. Il nuovo elemento contiene le impostazioni che un gestore <xref:System.Configuration.IConfigurationSectionHandler> della sezione di configurazione (ovvero, una classe che implementa l'interfaccia) legge. Gli attributi e gli elementi figlio di una sezione definita dipendono dal gestore di sezione utilizzato per leggere le impostazioni.

La dichiarazione di un gestore della sezione di configurazione nel file *Machine.config* consente di utilizzare la sezione di configurazione in qualsiasi file di configurazione dell'applicazione in tale computer, a meno che l'attributo **allowDefinition** non specifichi diversamente.

## <a name="example"></a>Esempio

L'esempio seguente mostra come definire una sezione di configurazione e definire le impostazioni per tale sezione:The following example shows how to define a configuration section and define settings for that section:

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

Questo elemento può essere utilizzato nei file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine.config*) e nei file *Web.config* che non si trovano a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedere anche

- [Schema del file di configurazione per .NET Framework](index.md)
