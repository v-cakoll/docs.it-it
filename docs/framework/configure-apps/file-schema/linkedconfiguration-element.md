---
title: '&lt;linkedConfiguration&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding/linkedConfiguration
- http://schemas.microsoft.com/.NetConfiguration/v2.0#linkedConfiguration
helpviewer_keywords:
- configuration files [.NET Framework],linked configuration files
- <linkedConfiguration> element
- including configuration files
- linked configuration files
- linkedConfiguration Element
ms.assetid: 8eb34f3b-427e-4288-a7ff-c73f489deb45
caps.latest.revision: "6"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: bfea438ec19303c35ad9d7a2816cb7b9473a00c0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="linkedconfiguration-element"></a>\<linkedConfiguration > elemento

Specifica un file di configurazione da includere.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<assemblyBinding >**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration >**

## <a name="syntax"></a>Sintassi

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a>Attributo

|           | Descrizione |
| --------- | ----------- |
| **href**  | Attributo obbligatorio.<br><br>L'URL del file di configurazione da includere. L'unico formato supportato per il **href** attributo `file://`. File locali e UNC file sono supportati. |

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ----------- |
| [**\<assemblyBinding >** elemento](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | Specifica i criteri di associazione degli assembly al livello di configurazione. |

## <a name="child-elements"></a>Elementi figlio

Nessuno

## <a name="remarks"></a>Note

Il  **\<linkedConfiguration >** elemento semplifica la gestione degli assembly del componente. Se una o più applicazioni utilizzano un assembly dotato di un file di configurazione che si trova in un percorso noto, è possono utilizzare i file di configurazione delle applicazioni che utilizzano l'assembly di  **\<linkedConfiguration >** elemento da includere il file di configurazione di assembly, anziché di includere le informazioni di configurazione direttamente. Quando viene gestita l'assembly del componente, l'aggiornamento del file di configurazione comuni fornisce informazioni di configurazione aggiornate per tutte le applicazioni che utilizzano l'assembly.

> [!NOTE]
> Il  **\<linkedConfiguration >** elemento non è supportato per le applicazioni con manifesti side-by-side di Windows.

Le regole seguenti determinano l'uso di file di configurazione collegati:

- Le impostazioni nel file di configurazione inclusi solo influisce sui criteri di associazione del caricatore e vengono utilizzate solo dal caricatore. I file di configurazione inclusi possono avere impostazioni diverse da quelle di criteri di associazione, ma tali impostazioni non hanno alcun effetto.

- L'unico formato supportato per il `href` attributo `file://`. File locali e UNC file sono supportati.

- È presente alcun vincolo al numero di configurazioni collegate per ogni file di configurazione.

- Tutti i file di configurazione collegati vengono uniti per formare un file, simile al comportamento del `#include` direttiva in C/C++.

- Il  **\<linkedConfiguration >** l'elemento è consentito solo nel file di configurazione dell'applicazione; viene ignorata *Machine. config*.

- I riferimenti circolari vengono rilevati e terminati. Ovvero, se il  **\<linkedConfiguration >** elementi di una serie di file di configurazione formano un ciclo, il ciclo viene rilevato e arrestato.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come includere i file di configurazione dal disco rigido locale:

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>Vedere anche

[**\<assemblyBinding >** elemento](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)   
[Schema di file di configurazione per .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
