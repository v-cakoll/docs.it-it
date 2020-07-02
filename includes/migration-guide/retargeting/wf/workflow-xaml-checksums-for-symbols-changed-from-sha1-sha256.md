---
ms.openlocfilehash: 946e71f2f466664c8f9fcf4811288ce693a872eb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616262"
---
### <a name="workflow-xaml-checksums-for-symbols-changed-from-sha1-to-sha256"></a>Checksum di Workflow XAML per i simboli modificati da SHA1 in SHA256

#### <a name="details"></a>Dettagli

Per supportare il debug con Visual Studio, il runtime di Workflow genera un checksum per un file Workflow XAML usando un algoritmo hash. In .NET Framework 4.6.2 e versioni precedenti, l'hash del checksum del flusso di lavoro usava l'algoritmo MD5, che causava problemi nei sistemi abilitati per FIPS. A partire da .NET Framework 4.7, l'algoritmo predefinito è stato modificato in SHA1. A partire da .NET Framework 4.8, l'algoritmo predefinito è stato modificato in SHA256.

#### <a name="suggestion"></a>Suggerimento

Se il codice non è in grado di caricare le istanze del flusso di lavoro o trovare i simboli appropriati a causa di un errore di checksum, provare a impostare l' `AppContext` opzione "Switch.System. Activities. UseSHA1HashForDebuggerSymbols "a `true` . Nel codice:

```csharp
System.AppContext.SetSwitch("Switch.System.Activities.UseSHA1HashForDebuggerSymbols", true);
```

O nella configurazione:

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Activities.UseSHA1HashForDebuggerSymbols=true" />
  </runtime>
</configuration>
```

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.8         |
| Type    | Ridestinazione |
