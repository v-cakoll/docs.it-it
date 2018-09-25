---
title: '&lt;linkedConfiguration&gt; elemento'
ms.date: 03/30/2017
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
author: mcleblanc
ms.author: markl
ms.openlocfilehash: c5186aa94993ba551252db6fef55853b5b554789
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170821"
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

nessuno

## <a name="remarks"></a>Note

Il  **\<linkedConfiguration >** elemento semplifica la gestione degli assembly del componente. Se uno o più applicazioni usano un assembly con un file di configurazione che si trova in un percorso noto, i file di configurazione delle applicazioni che usano l'assembly è possono usare la  **\<linkedConfiguration >** elemento da includere il file di configurazione di assembly, anziché includere le informazioni di configurazione direttamente. Quando viene gestita l'assembly del componente, l'aggiornamento del file di configurazione comune fornisce informazioni di configurazione aggiornate per tutte le applicazioni che usano l'assembly.

> [!NOTE]
> Il  **\<linkedConfiguration >** elemento non è supportato per le applicazioni con i manifesti side-by-side di Windows.

Le regole seguenti determinano l'uso di file di configurazione collegati:

- Le impostazioni nel file di configurazione inclusi solo influisce sui criteri di associazione del caricatore e vengono usate solo dal caricatore. I file di configurazione inclusi possono avere impostazioni diverse da quelle di criteri di associazione, ma tali impostazioni non hanno alcun effetto.

- L'unico formato supportato per il `href` attributo è `file://`. File locali e UNC file sono supportati.

- È presente alcun vincolo per il numero di configurazioni collegate per ogni file di configurazione.

- Tutti i file di configurazione collegati vengono uniti per formare un file, analogamente al comportamento del `#include` direttiva in C/C++.

- Il  **\<linkedConfiguration >** l'elemento è consentito solo nei file di configurazione dell'applicazione; viene ignorata nelle *Machine. config*.

- I riferimenti circolari vengono rilevati e terminati. Vale a dire, se il  **\<linkedConfiguration >** elementi di una serie di file di configurazione formano un ciclo, il ciclo viene rilevato e arrestato.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come includere il file di configurazione dal disco rigido locale:

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
