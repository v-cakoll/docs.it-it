---
ms.openlocfilehash: 9520f8c6b6671917f5694bc602293a00e2dab82d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568194"
---
### <a name="ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes"></a>La voce non gestisce più gli archivi con dimensioni di voce incoerenti

Gli archivi zip elencano sia le dimensioni compresse che le dimensioni non compresse nella directory centrale e nell'intestazione locale.  Anche i dati di entrata ne indicano le dimensioni.  In .NET Core 2.2 e versioni precedenti, questi valori non sono mai stati verificati per verificarne la coerenza. A partire da .NET Core 3.0, ora lo sono.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Core 2.2 <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> e versioni precedenti, ha esito positivo anche se l'intestazione locale non è in disaccordo con l'intestazione centrale del file zip. I dati vengono decompressi fino al raggiungimento della fine del flusso compresso, anche se la sua lunghezza supera la dimensione del file non compresso elencato nella directory centrale/intestazione locale.

A partire da .NET Core <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> 3.0, il metodo verifica che l'intestazione locale e l'intestazione centrale concordino sulle dimensioni compresse e non compresse di una voce.  In caso contrario, il <xref:System.IO.InvalidDataException> metodo genera un'eccezione se l'intestazione locale dell'archivio e/o le dimensioni dell'elenco dei descrittori di dati non sono d'accordo con la directory centrale del file zip. Durante la lettura di una voce, i dati decompressi vengono troncati alla dimensione del file non compresso elencato nell'intestazione.

Questa modifica è stata <xref:System.IO.Compression.ZipArchiveEntry> apportata per garantire che un rappresenta correttamente la dimensione dei dati e che solo la quantità di dati viene letta.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

Riconfezionare qualsiasi archivio zip che presenta questi problemi.

#### <a name="category"></a>Category

CoreFx

#### <a name="affected-apis"></a>API interessate

- <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFileExtensions.ExtractToDirectory%2A?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.ExtractToDirectory%2A?displayProperty=nameWithType>

<!--

### Affected APIs

`M:System.IO.Compression.ZipArchiveEntry.Open`
`Overload:System.IO.Compression.ZipFileExtensions.ExtractToDirectory%2A`
`Overload:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A`
`Overload:System.IO.Compression.ZipFile.ExtractToDirectory%2A`

-->
