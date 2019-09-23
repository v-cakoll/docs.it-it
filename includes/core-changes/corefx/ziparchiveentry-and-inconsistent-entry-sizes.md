---
ms.openlocfilehash: 604a67d1bea219b8eee2e7ac21040666083664ee
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181959"
---
### <a name="ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes"></a>ZipArchiveEntry non gestisce più gli archivi con dimensioni di voce incoerenti

Gli archivi zip elencano le dimensioni compresse e le dimensioni non compresse nella directory centrale e nell'intestazione locale.  Anche i dati di immissione indicano le relative dimensioni.  In .NET Core 2,2 e versioni precedenti, questi valori non venivano mai controllati per verificarne la coerenza. A partire da .NET Core 3,0, sono ora disponibili.

#### <a name="change-description"></a>Descrizione della modifica

In .NET Core 2,2 e versioni precedenti, <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> ha esito positivo anche se l'intestazione locale non accetta l'intestazione centrale del file zip. I dati vengono decompressi fino a quando non viene raggiunta la fine del flusso compresso, anche se la lunghezza supera la dimensione del file non compresso elencata nell'intestazione directory centrale/locale.

A partire da .NET Core 3,0, <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> il metodo verifica che l'intestazione locale e l'intestazione centrale accettino le dimensioni compresse e non compresse di una voce.  In caso contrario, il metodo genera un' <xref:System.IO.InvalidDataException> eccezione se l'intestazione locale dell'archivio e/o le dimensioni dell'elenco descrittore dati non sono consentite con la directory centrale del file zip. Quando si legge una voce, i dati decompressi vengono troncati nelle dimensioni dei file non compressi elencati nell'intestazione.

Questa modifica è stata apportata per <xref:System.IO.Compression.ZipArchiveEntry> garantire che un oggetto rappresenti correttamente le dimensioni dei propri dati e che venga letta solo tale quantità di dati.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

Riassemblare qualsiasi archivio zip che presenta questi problemi.

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

