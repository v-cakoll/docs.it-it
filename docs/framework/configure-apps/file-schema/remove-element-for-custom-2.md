---
title: <remove> elemento per NameValueSectionHandler e DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 062aa3921d29cffd33db2d96096ef25c2b819030
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300704"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<rimuovere > elemento per NameValueSectionHandler e DictionarySectionHandler

Rimuove un'impostazione definita in precedenza.

[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[ **\<sectionName>** ](~/docs/framework/configure-apps/file-schema/custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<remove>**

## <a name="syntax"></a>Sintassi

```xml
<add remove="key" />
```

## <a name="attribute"></a>Attributo

|           | Descrizione |
| --------- | ----------- |
| **key**   | Attributo obbligatorio.<br><br>Specifica il nome dell'impostazione da rimuovere. |

## <a name="parent-element"></a>Elemento padre

| Elemento | Descrizione |
| ------- | ------------|
| [ **\<sectionName >** elemento](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | Definisce le impostazioni per le sezioni di configurazione personalizzati che usano il <xref:System.Configuration.NameValueSectionHandler> e <xref:System.Configuration.DictionarySectionHandler> classi. |

## <a name="child-elements"></a>Elementi figlio

nessuno

## <a name="remarks"></a>Note

È possibile usare la  **\<rimuovere >** elemento da cui rimuovere le impostazioni dall'applicazione che sono stati definiti a un livello superiore nella gerarchia di file di configurazione.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come utilizzare il  **\<rimuovere >** elemento in un file di configurazione dell'applicazione per rimuovere le impostazioni definite in precedenza nel file di configurazione del computer.

Il codice di file di configurazione macchina seguente dichiara la sezione  **\<mySection >** e aggiunge due impostazioni `key1` e `key2`, a esso:

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

Il codice di file di configurazione dell'applicazione seguente rimuove il `key2` impostazione dal  **\<mySection >** :

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>File di configurazione

Questo elemento può essere usato nel file di configurazione dell'applicazione, file di configurazione computer (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.

## <a name="see-also"></a>Vedere anche

- [Schema di file di configurazione per .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
