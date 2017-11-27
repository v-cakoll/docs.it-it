---
title: '&lt;sezione&gt; elemento'
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c8ed8b0211c8366d799fe158d91dcb42f92ad0cf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="section-element"></a>\<sezione > elemento

Contiene una dichiarazione di sezione di configurazione.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<sezione >**

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup >**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md)   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sezione >**

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
| **type**  | Specifica il nome della classe del gestore della sezione configurazione che consente di leggere la sezione dal file di configurazione. Il valore del tipo presenta la sintassi "fully-qualified-section-handler-class-name, nome dell'assembly semplice". Il nome semplice dell'assembly è il nome del file principale senza la *DLL* estensione di file. |

## <a name="optional-attributes"></a>Attributi facoltativi

Gli attributi seguenti sono applicabili solo per le applicazioni ASP.NET. Il sistema di configurazione ignora questi attributi per gli altri tipi di applicazione.

|                     | Descrizione |
| ------------------- | ----------- |
| **allowDefinition** | Specifica il file di configurazione è possibile utilizzare la sezione in. Usare uno dei valori indicati di seguito.<br><br>**Ovunque**<br>Consente di essere usato in qualsiasi file di configurazione la sezione. Questa è l'impostazione predefinita.<br>**MachineOnly**<br>Consente la sezione da utilizzare solo nel file di configurazione del computer (*Machine. config*).<br>**MachineToApplication**<br>Consente la sezione da utilizzare nel file di configurazione del computer o il file di configurazione dell'applicazione. |
| **allowLocation**   | Determina se la sezione può essere utilizzata all'interno di  **\<percorso >** elemento. Usare uno dei valori indicati di seguito.<br><br>**true**<br>Consente la sezione all'interno di  **\<percorso >** elemento. Questa è l'impostazione predefinita.<br>**false**<br>Non consente la sezione all'interno di  **\<percorso >** elemento. |

## <a name="parent-elements"></a>Elementi padre

|     | Descrizione |
| --- | ----------- |
| [**\<configSections >** elemento](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | Contiene le dichiarazioni dello spazio dei nomi e di sezione di configurazione. |
| [**\<sectionGroup >** elemento](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | Definisce uno spazio dei nomi per le sezioni di configurazione. |

> [!NOTE]
> Oggetto  **\<sezione >** elemento è un elemento figlio di uno  **\<configSections >** o  **\<sectionGroup >** ma non entrambi.

## <a name="child-elements"></a>Elementi figlio

Nessuno

## <a name="remarks"></a>Note

La dichiarazione essenzialmente di una sezione di configurazione definisce un nuovo elemento per il file di configurazione. Il nuovo elemento contiene le impostazioni di gestore della sezione di configurazione (vale a dire, una classe che implementa il <xref:System.Configuration.IConfigurationSectionHandler> interface) legge. Gli attributi e gli elementi figlio di una sezione che definire dipendono dal gestore della sezione utilizzato per la lettura delle impostazioni.

Dichiarazione di un gestore della sezione di configurazione nel *Machine. config* file consente di utilizzare la sezione di configurazione in qualsiasi file di configurazione dell'applicazione nel computer, a meno che il **allowDefinition**attributo specifica in caso contrario.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come definire una sezione di configurazione e impostazioni per la sezione:

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

Questo elemento può essere usato nel file di configurazione dell'applicazione, i file di configurazione macchina (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedere anche

[Schema di file di configurazione per .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
