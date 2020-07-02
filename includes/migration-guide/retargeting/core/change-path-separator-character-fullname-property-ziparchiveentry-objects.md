---
ms.openlocfilehash: 148312743dd274728b178951548889dc3a680528
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614465"
---
### <a name="change-in-path-separator-character-in-fullname-property-of-ziparchiveentry-objects"></a>Modifica del carattere separatore di percorso nella proprietà FullName degli oggetti ZipArchiveEntry

#### <a name="details"></a>Dettagli

Per le app destinate a .NET Framework 4.6.1 e versioni successive, il carattere separatore di percorso è stato modificato da una barra rovesciata (" \" ) a una barra ("/") nella <xref:System.IO.Compression.ZipArchiveEntry.FullName> proprietà degli <xref:System.IO.Compression.ZipArchiveEntry> oggetti creati da overload del <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A> metodo. Questa modifica garantisce la conformità dell'implementazione .NET alla sezione 4.4.17.1 della [specifica relativa al formato di file ZIP](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) e consente agli archivi con estensione ZIP di essere decompressi anche in sistemi non Windows.<br />La decompressione di un file ZIP creato da un'applicazione che ha come destinazione una versione precedente di .NET Framework nei sistemi operativi non Windows, ad esempio Macintosh, non riesce a mantenere la struttura della directory. Ad esempio, su Macintosh, viene creato un set di file il cui nome file concatena il percorso della directory, insieme a tutti i caratteri di barra rovesciata ("") e al nome del file. Di conseguenza, la struttura di directory dei file decompressi non viene mantenuta.

#### <a name="suggestion"></a>Suggerimento

L'effetto di questa modifica su. I file ZIP decompressi nel sistema operativo Windows dalle API nello <xref:System.IO?displayProperty=nameWithType> spazio dei nomi .NET Framework devono essere minimi, poiché queste API possono gestire facilmente una barra ("/") o una barra rovesciata (" \" ) come carattere separatore di percorso.<br />Se questa modifica è indesiderata, è possibile rifiutarla esplicitamente aggiungendo un'impostazione di configurazione alla [<](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) sezione del file di configurazione dell'applicazione. L'esempio seguente mostra sia la sezione `<runtime>` che l'opzione per il rifiuto esplicito `Switch.System.IO.Compression.ZipFile.UseBackslash`:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />
</runtime>
```

Inoltre, le app destinate alle versioni precedenti del .NET Framework ma sono in esecuzione nel .NET Framework 4.6.1 e versioni successive possono acconsentire esplicitamente a questo comportamento aggiungendo un'impostazione di configurazione alla [<](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) sezione del file di configurazione dell'applicazione. L'esempio seguente mostra sia la sezione `<runtime>` che l'opzione per il consenso esplicito `Switch.System.IO.Compression.ZipFile.UseBackslash`.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />
</runtime>
```

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.6.1       |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean)?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean,System.Text.Encoding)?displayProperty=nameWithType>
