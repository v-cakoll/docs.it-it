---
ms.openlocfilehash: 9520f8c6b6671917f5694bc602293a00e2dab82d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568194"
---
### <a name="ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes"></a><span data-ttu-id="542f9-101">La voce non gestisce più gli archivi con dimensioni di voce incoerenti</span><span class="sxs-lookup"><span data-stu-id="542f9-101">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>

<span data-ttu-id="542f9-102">Gli archivi zip elencano sia le dimensioni compresse che le dimensioni non compresse nella directory centrale e nell'intestazione locale.</span><span class="sxs-lookup"><span data-stu-id="542f9-102">Zip archives list both compressed size and uncompressed size in the central directory and local header.</span></span>  <span data-ttu-id="542f9-103">Anche i dati di entrata ne indicano le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="542f9-103">The entry data itself also indicates its size.</span></span>  <span data-ttu-id="542f9-104">In .NET Core 2.2 e versioni precedenti, questi valori non sono mai stati verificati per verificarne la coerenza.</span><span class="sxs-lookup"><span data-stu-id="542f9-104">In .NET Core 2.2 and earlier versions, these values were never checked for consistency.</span></span> <span data-ttu-id="542f9-105">A partire da .NET Core 3.0, ora lo sono.</span><span class="sxs-lookup"><span data-stu-id="542f9-105">Starting with .NET Core 3.0, they now are.</span></span>

#### <a name="change-description"></a><span data-ttu-id="542f9-106">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="542f9-106">Change description</span></span>

<span data-ttu-id="542f9-107">In .NET Core 2.2 <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> e versioni precedenti, ha esito positivo anche se l'intestazione locale non è in disaccordo con l'intestazione centrale del file zip.</span><span class="sxs-lookup"><span data-stu-id="542f9-107">In .NET Core 2.2 and earlier versions, <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> succeeds even if the local header disagrees with the central header of the zip file.</span></span> <span data-ttu-id="542f9-108">I dati vengono decompressi fino al raggiungimento della fine del flusso compresso, anche se la sua lunghezza supera la dimensione del file non compresso elencato nella directory centrale/intestazione locale.</span><span class="sxs-lookup"><span data-stu-id="542f9-108">Data is decompressed until the end of the compressed stream is reached, even if its length exceeds the uncompressed file size listed in the central directory/local header.</span></span>

<span data-ttu-id="542f9-109">A partire da .NET Core <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> 3.0, il metodo verifica che l'intestazione locale e l'intestazione centrale concordino sulle dimensioni compresse e non compresse di una voce.</span><span class="sxs-lookup"><span data-stu-id="542f9-109">Starting with .NET Core 3.0, the <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> method checks that local header and central header agree on compressed and uncompressed sizes of an entry.</span></span>  <span data-ttu-id="542f9-110">In caso contrario, il <xref:System.IO.InvalidDataException> metodo genera un'eccezione se l'intestazione locale dell'archivio e/o le dimensioni dell'elenco dei descrittori di dati non sono d'accordo con la directory centrale del file zip.</span><span class="sxs-lookup"><span data-stu-id="542f9-110">If they do not, the method throws an <xref:System.IO.InvalidDataException> if the archive's local header and/or data descriptor list sizes that disagree with the central directory of the zip file.</span></span> <span data-ttu-id="542f9-111">Durante la lettura di una voce, i dati decompressi vengono troncati alla dimensione del file non compresso elencato nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="542f9-111">When reading an entry, decompressed data is truncated to the uncompressed file size listed in the header.</span></span>

<span data-ttu-id="542f9-112">Questa modifica è stata <xref:System.IO.Compression.ZipArchiveEntry> apportata per garantire che un rappresenta correttamente la dimensione dei dati e che solo la quantità di dati viene letta.</span><span class="sxs-lookup"><span data-stu-id="542f9-112">This change was made to ensure that a <xref:System.IO.Compression.ZipArchiveEntry> correctly represents the size of its data and that only that amount of data is read.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="542f9-113">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="542f9-113">Version introduced</span></span>

<span data-ttu-id="542f9-114">3.0</span><span class="sxs-lookup"><span data-stu-id="542f9-114">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="542f9-115">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="542f9-115">Recommended action</span></span>

<span data-ttu-id="542f9-116">Riconfezionare qualsiasi archivio zip che presenta questi problemi.</span><span class="sxs-lookup"><span data-stu-id="542f9-116">Repackage any zip archive that exhibits these problems.</span></span>

#### <a name="category"></a><span data-ttu-id="542f9-117">Category</span><span class="sxs-lookup"><span data-stu-id="542f9-117">Category</span></span>

<span data-ttu-id="542f9-118">CoreFx</span><span class="sxs-lookup"><span data-stu-id="542f9-118">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="542f9-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="542f9-119">Affected APIs</span></span>

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
