---
title: Elemento <assemblyBinding> per <configuration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: 21cf5e749b0dae310c3326f8abf82c6678fc97e9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155479"
---
# <a name="assemblybinding-element-for-configuration"></a>Elemento \<assemblyBinding> per \<configuration>

Specifica i criteri di associazione degli assembly al livello di configurazione.

[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**

## <a name="syntax"></a>Sintassi

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a>Attributo

|           | Descrizione |
| --------- | ----------- |
| **xmlns** | Attributo obbligatorio.<br><br>Specifica lo spazio dei nomi XML necessario per il binding di assembly. Usare la stringa "urn:schemas-microsoft-com:asm.v1" come valore. |

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework. |

## <a name="child-element"></a>Elemento figlio

|     | Descrizione |
| --- | ----------- |
| [**\<linkedConfiguration>**](linkedconfiguration-element.md) | Specifica un file di configurazione da includere. |

## <a name="remarks"></a>Commenti

L' [**\<linkedConfiguration>**](linkedconfiguration-element.md) elemento semplifica la gestione degli assembly dei componenti consentendo ai file di configurazione dell'applicazione di includere i file di configurazione degli assembly in posizioni note, anziché duplicare le impostazioni di configurazione degli assembly.

> [!NOTE]
> L' **\<linkedConfiguration>** elemento non è supportato per le applicazioni con manifesti affiancati di Windows.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come includere un file di configurazione nel disco rigido locale:

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>Vedi anche

- [Schema del file di configurazione per il .NET Framework](index.md)
