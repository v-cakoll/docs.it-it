---
title: Elemento <linkedConfiguration>
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
ms.openlocfilehash: 14ee2275ecf690ab16ffaabd71fbbe7e1a4897bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74087969"
---
# <a name="linkedconfiguration-element"></a>Elemento \<linkedConfiguration>

Specifica un file di configurazione da includere.

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**

## <a name="syntax"></a>Sintassi

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a>Attributo

|           | Descrizione |
| --------- | ----------- |
| **href**  | Attributo obbligatorio.<br><br>URL del file di configurazione da includere. L'unico formato supportato per l'attributo **href** è `file://` . I file locali e i file UNC sono supportati. |

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ----------- |
| [**\<assemblyBinding>** Elemento](assemblybinding-element-for-configuration.md) | Specifica i criteri di associazione degli assembly al livello di configurazione. |

## <a name="child-elements"></a>Elementi figlio

nessuno

## <a name="remarks"></a>Osservazioni

L' **\<linkedConfiguration>** elemento semplifica la manutenzione degli assembly del componente. Se una o più applicazioni utilizzano un assembly con un file di configurazione che risiede in un percorso noto, i file di configurazione delle applicazioni che utilizzano l'assembly possono utilizzare l' **\<linkedConfiguration>** elemento per includere il file di configurazione dell'assembly, anziché includere direttamente le informazioni di configurazione. Quando l'assembly del componente viene servito, l'aggiornamento del file di configurazione comune fornisce informazioni di configurazione aggiornate a tutte le applicazioni che utilizzano l'assembly.

> [!NOTE]
> L' **\<linkedConfiguration>** elemento non è supportato per le applicazioni con manifesti affiancati di Windows.

Le regole seguenti regolano l'utilizzo dei file di configurazione collegati:

- Le impostazioni nei file di configurazione inclusi influiscono solo sui criteri di associazione del caricatore e vengono usate solo dal caricatore. I file di configurazione inclusi possono avere impostazioni diverse dai criteri di associazione, ma tali impostazioni non hanno alcun effetto.

- L'unico formato supportato per l' `href` attributo è `file://` . I file locali e i file UNC sono supportati.

- Non esiste alcun vincolo sul numero di configurazioni collegate per ogni file di configurazione.

- Tutti i file di configurazione collegati vengono uniti per formare un file, in modo analogo al comportamento della `#include` direttiva in C/C++.

- L' **\<linkedConfiguration>** elemento è consentito solo nei file di configurazione dell'applicazione, ma viene ignorato in *Machine. config*.

- I riferimenti circolari vengono rilevati e terminati. Ovvero, se gli **\<linkedConfiguration>** elementi di una serie di file di configurazione formano un ciclo, il ciclo viene rilevato e arrestato.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come includere il file di configurazione dal disco rigido locale:

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>Vedi anche

- [**\<assemblyBinding>** Elemento](assemblybinding-element-for-configuration.md)
- [Schema del file di configurazione per il .NET Framework](index.md)
