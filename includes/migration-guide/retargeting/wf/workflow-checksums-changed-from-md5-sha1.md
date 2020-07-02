---
ms.openlocfilehash: 72d48d1daa85b6891c122f2fcc5279642253b926
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614840"
---
### <a name="workflow-checksums-changed-from-md5-to-sha1"></a>Checksum del flusso di lavoro modificati da MD5 a SHA1

#### <a name="details"></a>Dettagli

Per supportare il debug con Visual Studio, il runtime del flusso di lavoro genera un checksum per un'istanza del flusso di lavoro usando un algoritmo hash. In .NET Framework 4.6.2 e versioni precedenti, l'hash del checksum del flusso di lavoro usava l'algoritmo MD5, che causava problemi nei sistemi abilitati per FIPS. A partire da .NET Framework 4.7 l'algoritmo è SHA1. Se il codice ha mantenuto i checksum, questi non saranno compatibili.

#### <a name="suggestion"></a>Suggerimento

Se il codice non riesce a caricare le istanze del flusso di lavoro a causa di un errore di checksum, provare a impostare lo switch `AppContext`&quot;Switch.System.Activities.UseMD5ForWFDebugger&quot; su true. Nel codice:

```csharp
System.AppContext.SetSwitch("Switch.System.Activities.UseMD5ForWFDebugger", true);
```

O nella configurazione:

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Activities.UseMD5ForWFDebugger=true" />
  </runtime>
</configuration>
```

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.7         |
| Type    | Ridestinazione |
