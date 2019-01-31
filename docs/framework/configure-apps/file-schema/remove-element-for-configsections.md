---
title: <remove> (elemento) per <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 9ceffd3194c7df41f12ac6cd6b589602965b4920
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55279097"
---
# <a name="remove-element-for-configsections"></a>\<rimuovere > (elemento) per \<configSections >

Rimuove una sezione predefiniti o un gruppo di sezioni.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a>Sintassi

```xml
<remove name="section name or section group name" />
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

È possibile usare la  **\<rimuovere >** elemento da rimuovere sezioni e gruppi dall'applicazione che sono stati definiti a un livello superiore nella gerarchia di file di configurazione.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come utilizzare il  **\<rimuovere >** elemento in un file di configurazione dell'applicazione per rimuovere una sezione definita in precedenza nel file di configurazione del computer.

Il codice di file di configurazione macchina seguente dichiara la sezione  **\<sampleSection >**:

```xml
<!-- Machine.config file -->
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

Il codice di file di configurazione dell'applicazione seguente rimuove il  **\<sampleSection >** sezione. Dopo la rimozione, l'applicazione non è possibile recuperare le impostazioni in  **\<sampleSection >**.

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a>File di configurazione

Questo elemento può essere usato nel file di configurazione dell'applicazione, file di configurazione computer (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedere anche

- [Schema di file di configurazione per .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
