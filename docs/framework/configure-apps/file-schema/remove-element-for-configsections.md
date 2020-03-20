---
title: Elemento <remove> per <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
ms.openlocfilehash: 6991e3f73ac180fc690ec48e1a0d15f40c915733
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154530"
---
# <a name="remove-element-for-configsections"></a>\<rimuovere>elemento \<per la> configSections

Rimuove una sezione o un gruppo di sezioni predefinito.

[**\<>di configurazione**](configuration-element.md)\
&nbsp;&nbsp;[**\<>configSections**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<rimuovere>**

## <a name="syntax"></a>Sintassi

```xml
<remove name="section name or section group name" />
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

È possibile ** \<** utilizzare l'elemento remove>per rimuovere sezioni e gruppi di sezioni dall'applicazione definiti a un livello superiore nella gerarchia dei file di configurazione.

## <a name="example"></a>Esempio

Nell'esempio seguente viene ** \<** illustrato come utilizzare l'elemento remove>in un file di configurazione dell'applicazione per rimuovere una sezione definita in precedenza nel file di configurazione del computer.

Il codice del file di configurazione del computer seguente dichiara la sezione ** \<sampleSection>**:

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

Il codice del file ** \<** di configurazione dell'applicazione seguente rimuove la sezione sampleSection>. Dopo la rimozione, l'applicazione non può recuperare le impostazioni in ** \<sampleSection>**.

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a>File di configurazione

Questo elemento può essere utilizzato nei file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine.config*) e nei file *Web.config* che non si trovano a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedere anche

- [Schema del file di configurazione per .NET Framework](index.md)
