---
ms.openlocfilehash: 53d74db1a77e62cc64250658281fd3e4706fe494
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614425"
---
### <a name="allow-unicode-bidirectional-control-characters-in-uris"></a>Consentire i caratteri di controllo bidirezionali Unicode negli URI

#### <a name="details"></a>Dettagli

La specifica Unicode include vari caratteri di controllo speciali, usati per indicare l'orientamento del testo. Nelle versioni precedenti di .NET Framework tali caratteri venivano erroneamente rimossi da tutti gli URI, anche se erano presenti con il formato di codifica con percentuali appropriato. Per una maggior conformità con [RFC 3987](https://tools.ietf.org/html/rfc3987), ora tali caratteri sono consentiti negli URI. Se vengono rilevati come non codificati in un URI, i caratteri vengono codificati con simboli di percentuale. Se sono già codificati con simboli di percentuale, vengono lasciati invariati.

#### <a name="suggestion"></a>Suggerimento

Per le applicazioni destinate alle versioni di .NET Framework a partire da 4.7.2 il supporto dei caratteri Unicode bidirezionali è abilitato per impostazione predefinita. Se questa modifica non è opportuna, è possibile disabilitarla aggiungendo l'opzione [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente alla sezione `<runtime>` del file di configurazione dell'app:

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=true" />
</runtime>
```

Per le applicazioni che sono destinate a versioni precedenti di .NET Framework ma vengono eseguite con versioni a partire da .NET Framework 4.7.2, il supporto per i caratteri Unicode bidirezionali è disabilitato per impostazione predefinita. È possibile abilitarlo aggiungendo l'opzione [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente alla sezione `<runtime>` del file di configurazione dell'app:

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=false" />
</runtime>
```

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.7.2       |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Uri?displayProperty=nameWithType>
