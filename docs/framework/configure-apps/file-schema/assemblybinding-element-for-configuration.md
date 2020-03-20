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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155479"
---
# <a name="assemblybinding-element-for-configuration"></a>\<elemento> assemblyBinding per \<la> configurazione

Specifica i criteri di associazione degli assembly al livello di configurazione.

[** \<>**](configuration-element.md) &nbsp; &nbsp; **assemblyBinding>\<**

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
| [**\<>di configurazione**](configuration-element.md) | Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework. |

## <a name="child-element"></a>Elemento figlio

|     | Descrizione |
| --- | ----------- |
| [**\<>linkedConfiguration**](linkedconfiguration-element.md) | Specifica un file di configurazione da includere. |

## <a name="remarks"></a>Osservazioni

Il [** \<>elemento linkedConfiguration**](linkedconfiguration-element.md) semplifica la gestione degli assembly dei componenti consentendo ai file di configurazione dell'applicazione di includere i file di configurazione dell'assembly in percorsi noti, anziché duplicare le impostazioni di configurazione dell'assembly.

> [!NOTE]
> L'elemento ** \<>linkedConfiguration** non è supportato per le applicazioni con manifesti affiancati di Windows.The linkedConfiguration>element is not supported for applications with Windows side-by-side manifests.

## <a name="example"></a>Esempio

L'esempio seguente mostra come includere un file di configurazione sul disco rigido locale:

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>Vedere anche

- [Schema del file di configurazione per .NET Framework](index.md)
