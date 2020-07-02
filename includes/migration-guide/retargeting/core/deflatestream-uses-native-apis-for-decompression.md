---
ms.openlocfilehash: 7e42a294b151d07a6fdc61308cdf92df7a31a1d6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614488"
---
### <a name="deflatestream-uses-native-apis-for-decompression"></a>DeflateStream usa API native per la decompressione

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.7.2 l'implementazione della decompressione nella classe `T:System.IO.Compression.DeflateStream` è stata modificata e ora usa le API Windows native per impostazione predefinita. In genere questo comporta un miglioramento significativo delle prestazioni. Tutte le applicazioni .NET destinate a .NET Framework 4.7.2 o versioni successive usano l'implementazione nativa. Questa modifica potrebbe causare alcune variazioni di comportamento, tra cui le seguenti:

- I messaggi di eccezione potrebbero essere diversi. Tuttavia il tipo di eccezione generato rimane invariato.
- È possibile che alcuni casi speciali, ad esempio il caso in cui la memoria non è sufficiente per completare un'operazione, vengano gestiti in modo diverso.
- Esistono differenze note per l'analisi dell'intestazione gzip (Nota: è interessata solo `GZipStream` impostata per la decompressione):
- Le eccezioni durante l'analisi delle intestazioni non valide possono essere attivate in momenti diversi.
- L'implementazione nativa impone che i valori di alcuni flag riservati nell'intestazione gzip (ad esempio [FLG](http://www.zlib.org/rfc-gzip.html#header-trailer)) vengano impostati in base alla specifica. Ciò può causare un'eccezione nei punti in cui i valori in precedenza non validi venivano ignorati.

#### <a name="suggestion"></a>Suggerimento

Se la decompressione con API native compromette il comportamento dell'app, è possibile rifiutare esplicitamente questa funzionalità aggiungendo l'opzione `Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression` alla sezione `runtime` del file app.config e impostandola su `true`:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression=true" />
  </runtime>
</configuration>
```

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.7.2       |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.IO.Compression.DeflateStream?displayProperty=nameWithType>
- <xref:System.IO.Compression.GZipStream?displayProperty=nameWithType>
