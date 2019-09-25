---
ms.openlocfilehash: 9520f8c6b6671917f5694bc602293a00e2dab82d
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "71217059"
---
### <a name="ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes"></a><span data-ttu-id="bd8e8-101">ZipArchiveEntry non gestisce più gli archivi con dimensioni di voce incoerenti</span><span class="sxs-lookup"><span data-stu-id="bd8e8-101">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>

<span data-ttu-id="bd8e8-102">Gli archivi zip elencano le dimensioni compresse e le dimensioni non compresse nella directory centrale e nell'intestazione locale.</span><span class="sxs-lookup"><span data-stu-id="bd8e8-102">Zip archives list both compressed size and uncompressed size in the central directory and local header.</span></span>  <span data-ttu-id="bd8e8-103">Anche i dati di immissione indicano le relative dimensioni.</span><span class="sxs-lookup"><span data-stu-id="bd8e8-103">The entry data itself also indicates its size.</span></span>  <span data-ttu-id="bd8e8-104">In .NET Core 2,2 e versioni precedenti, questi valori non venivano mai controllati per verificarne la coerenza.</span><span class="sxs-lookup"><span data-stu-id="bd8e8-104">In .NET Core 2.2 and earlier versions, these values were never checked for consistency.</span></span> <span data-ttu-id="bd8e8-105">A partire da .NET Core 3,0, sono ora disponibili.</span><span class="sxs-lookup"><span data-stu-id="bd8e8-105">Starting with .NET Core 3.0, they now are.</span></span>

#### <a name="change-description"></a><span data-ttu-id="bd8e8-106">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="bd8e8-106">Change description</span></span>

<span data-ttu-id="bd8e8-107">In .NET Core 2,2 e versioni precedenti, <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> ha esito positivo anche se l'intestazione locale non accetta l'intestazione centrale del file zip.</span><span class="sxs-lookup"><span data-stu-id="bd8e8-107">In .NET Core 2.2 and earlier versions, <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> succeeds even if the local header disagrees with the central header of the zip file.</span></span> <span data-ttu-id="bd8e8-108">I dati vengono decompressi fino a quando non viene raggiunta la fine del flusso compresso, anche se la lunghezza supera la dimensione del file non compresso elencata nell'intestazione directory centrale/locale.</span><span class="sxs-lookup"><span data-stu-id="bd8e8-108">Data is decompressed until the end of the compressed stream is reached, even if its length exceeds the uncompressed file size listed in the central directory/local header.</span></span>

<span data-ttu-id="bd8e8-109">A partire da .NET Core 3,0, <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> il metodo verifica che l'intestazione locale e l'intestazione centrale accettino le dimensioni compresse e non compresse di una voce.</span><span class="sxs-lookup"><span data-stu-id="bd8e8-109">Starting with .NET Core 3.0, the <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> method checks that local header and central header agree on compressed and uncompressed sizes of an entry.</span></span>  <span data-ttu-id="bd8e8-110">In caso contrario, il metodo genera un' <xref:System.IO.InvalidDataException> eccezione se l'intestazione locale dell'archivio e/o le dimensioni dell'elenco descrittore dati non sono consentite con la directory centrale del file zip.</span><span class="sxs-lookup"><span data-stu-id="bd8e8-110">If they do not, the method throws an <xref:System.IO.InvalidDataException> if the archive's local header and/or data descriptor list sizes that disagree with the central directory of the zip file.</span></span> <span data-ttu-id="bd8e8-111">Quando si legge una voce, i dati decompressi vengono troncati nelle dimensioni dei file non compressi elencati nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="bd8e8-111">When reading an entry, decompressed data is truncated to the uncompressed file size listed in the header.</span></span>

<span data-ttu-id="bd8e8-112">Questa modifica è stata apportata per <xref:System.IO.Compression.ZipArchiveEntry> garantire che un oggetto rappresenti correttamente le dimensioni dei propri dati e che venga letta solo tale quantità di dati.</span><span class="sxs-lookup"><span data-stu-id="bd8e8-112">This change was made to ensure that a <xref:System.IO.Compression.ZipArchiveEntry> correctly represents the size of its data and that only that amount of data is read.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="bd8e8-113">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="bd8e8-113">Version introduced</span></span>

<span data-ttu-id="bd8e8-114">3.0</span><span class="sxs-lookup"><span data-stu-id="bd8e8-114">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="bd8e8-115">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="bd8e8-115">Recommended action</span></span>

<span data-ttu-id="bd8e8-116">Riassemblare qualsiasi archivio zip che presenta questi problemi.</span><span class="sxs-lookup"><span data-stu-id="bd8e8-116">Repackage any zip archive that exhibits these problems.</span></span>

#### <a name="category"></a><span data-ttu-id="bd8e8-117">Category</span><span class="sxs-lookup"><span data-stu-id="bd8e8-117">Category</span></span>

<span data-ttu-id="bd8e8-118">CoreFx</span><span class="sxs-lookup"><span data-stu-id="bd8e8-118">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bd8e8-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="bd8e8-119">Affected APIs</span></span>

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
