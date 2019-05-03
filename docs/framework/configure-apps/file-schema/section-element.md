---
title: <section> elemento
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 58f823ce0c128f30e361b4a631d41286533b5f0f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701502"
---
# <a name="section-element"></a>\<sezione > elemento

Contiene una dichiarazione della sezione di configurazione.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md)   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**

## <a name="syntax"></a>Sintassi

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a>Attributi obbligatori

|           | Descrizione |
| --------- | ----------- |
| **name**  | Specifica il nome della sezione di configurazione. |
| **type**  | Specifica il nome della classe del gestore della sezione configurazione che legge la sezione dal file di configurazione. Il valore del tipo presenta la sintassi "fully-qualified-section-handler-class-name, simple-assembly-name". Il nome semplice dell'assembly è il nome file radice senza il *DLL* estensione di file. |

## <a name="optional-attributes"></a>Attributi facoltativi

Gli attributi seguenti sono applicabili solo per le applicazioni ASP.NET. Il sistema di configurazione ignora questi attributi per gli altri tipi di applicazione.

|                     | Descrizione |
| ------------------- | ----------- |
| **allowDefinition** | Specifica la sezione può essere usata in quale file di configurazione. Usare uno dei valori indicati di seguito.<br><br>**Everywhere**<br>Consente la sezione da usare in qualsiasi file di configurazione. Questa è l'impostazione predefinita.<br>**MachineOnly**<br>Consente la sezione da utilizzare solo nel file di configurazione del computer (*Machine. config*).<br>**MachineToApplication**<br>Consente la sezione da utilizzare nel file di configurazione del computer o il file di configurazione dell'applicazione. |
| **allowLocation**   | Determina se la sezione può essere utilizzata all'interno di  **\<location >** elemento. Usare uno dei valori indicati di seguito.<br><br>**true**<br>Consente la sezione da usare all'interno di  **\<location >** elemento. Questa è l'impostazione predefinita.<br>**false**<br>Non consente la sezione da usare all'interno di  **\<location >** elemento. |

## <a name="parent-elements"></a>Elementi padre

|     | Descrizione |
| --- | ----------- |
| [**\<configSections >** elemento](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | Contiene le dichiarazioni dello spazio dei nomi e sezione di configurazione. |
| [**\<sectionGroup >** elemento](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | Definisce uno spazio dei nomi per le sezioni di configurazione. |

> [!NOTE]
> Oggetto  **\<sezione >** è un elemento figlio di uno  **\<configSections >** oppure  **\<sectionGroup >** ma non entrambi.

## <a name="child-elements"></a>Elementi figlio

nessuno

## <a name="remarks"></a>Note

Essenzialmente la dichiarazione di una sezione di configurazione definisce un nuovo elemento per il file di configurazione. Il nuovo elemento contiene le impostazioni della sezione di gestore di configurazione (vale a dire, una classe che implementa il <xref:System.Configuration.IConfigurationSectionHandler> interface) legge. Gli attributi e gli elementi figlio di una sezione che è definire variano a seconda del gestore della sezione utilizzato per la lettura delle impostazioni.

La dichiarazione di un gestore della sezione di configurazione nel *Machine. config* file consente di usare la sezione di configurazione in qualsiasi file di configurazione dell'applicazione nello stesso computer, a meno che non la **allowDefinition**attributo specifichi diversamente.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come definire una sezione di configurazione e definire le impostazioni per tale sezione:

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

Questo elemento può essere usato nel file di configurazione dell'applicazione, file di configurazione computer (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedere anche

- [Schema di file di configurazione per .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
