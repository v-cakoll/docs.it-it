---
title: Elemento <remove> per <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
ms.openlocfilehash: 99d67bd621390789993caa4862e5ce379135eb92
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215383"
---
# <a name="remove-element-for-configsections"></a>\<rimuovere > elemento per \<configSections >

Rimuove una sezione o un gruppo di sezioni predefinito.

[ **\<configuration>** ](configuration-element.md)\
&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<rimuovi >**

## <a name="syntax"></a>Sintassi

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a>Attributo

|           | Descrizione |
| --------- | ----------- |
| **nome**  | Attributo obbligatorio.<br><br>Specifica il nome della sezione o del gruppo di sezioni da rimuovere. |

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ----------- |
| [ **\<configSections >** Elemento](configsections-element-for-configuration.md) | Contiene la sezione di configurazione e le dichiarazioni dello spazio dei nomi. |

## <a name="child-elements"></a>Elementi figlio

nessuno

## <a name="remarks"></a>Osservazioni

È possibile utilizzare l'elemento **\<remove >** per rimuovere sezioni e gruppi di sezioni dall'applicazione definiti a un livello superiore nella gerarchia dei file di configurazione.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come utilizzare l'elemento **\<remove >** in un file di configurazione dell'applicazione per rimuovere una sezione precedentemente definita nel file di configurazione del computer.

Il seguente codice del file di configurazione del computer dichiara la sezione **\<sampleSection >** :

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

Il codice del file di configurazione dell'applicazione seguente rimuove la sezione **\<> sampleSection** . Dopo la rimozione, l'applicazione non è in grado di recuperare le impostazioni in **\<> sampleSection**.

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a>File di configurazione

Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedere anche

- [Schema del file di configurazione per il .NET Framework](index.md)
