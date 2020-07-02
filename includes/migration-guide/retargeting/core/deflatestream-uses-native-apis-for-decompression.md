---
ms.openlocfilehash: 7e42a294b151d07a6fdc61308cdf92df7a31a1d6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614488"
---
### <a name="deflatestream-uses-native-apis-for-decompression"></a><span data-ttu-id="0174d-101">DeflateStream usa API native per la decompressione</span><span class="sxs-lookup"><span data-stu-id="0174d-101">DeflateStream uses native APIs for decompression</span></span>

#### <a name="details"></a><span data-ttu-id="0174d-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0174d-102">Details</span></span>

<span data-ttu-id="0174d-103">A partire da .NET Framework 4.7.2 l'implementazione della decompressione nella classe `T:System.IO.Compression.DeflateStream` è stata modificata e ora usa le API Windows native per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0174d-103">Starting with the .NET Framework 4.7.2, the implementation of decompression in the `T:System.IO.Compression.DeflateStream` class has changed to use native Windows APIs by default.</span></span> <span data-ttu-id="0174d-104">In genere questo comporta un miglioramento significativo delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="0174d-104">Typically, this results in a substantial performance improvement.</span></span> <span data-ttu-id="0174d-105">Tutte le applicazioni .NET destinate a .NET Framework 4.7.2 o versioni successive usano l'implementazione nativa. Questa modifica potrebbe causare alcune variazioni di comportamento, tra cui le seguenti:</span><span class="sxs-lookup"><span data-stu-id="0174d-105">All .NET applications targeting the .NET Framework version 4.7.2 or higher use the native implementation.This change might result in some differences in behavior, which include:</span></span>

- <span data-ttu-id="0174d-106">I messaggi di eccezione potrebbero essere diversi.</span><span class="sxs-lookup"><span data-stu-id="0174d-106">Exception messages may be different.</span></span> <span data-ttu-id="0174d-107">Tuttavia il tipo di eccezione generato rimane invariato.</span><span class="sxs-lookup"><span data-stu-id="0174d-107">However, the type of exception thrown remains the same.</span></span>
- <span data-ttu-id="0174d-108">È possibile che alcuni casi speciali, ad esempio il caso in cui la memoria non è sufficiente per completare un'operazione, vengano gestiti in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="0174d-108">Some special situations, such as not having enough memory to complete an operation, may be handled differently.</span></span>
- <span data-ttu-id="0174d-109">Esistono differenze note per l'analisi dell'intestazione gzip (Nota: è interessata solo `GZipStream` impostata per la decompressione):</span><span class="sxs-lookup"><span data-stu-id="0174d-109">There are known differences for parsing gzip header (note: only `GZipStream` set for decompression is affected):</span></span>
- <span data-ttu-id="0174d-110">Le eccezioni durante l'analisi delle intestazioni non valide possono essere attivate in momenti diversi.</span><span class="sxs-lookup"><span data-stu-id="0174d-110">Exceptions when parsing invalid headers may be thrown at different times.</span></span>
- <span data-ttu-id="0174d-111">L'implementazione nativa impone che i valori di alcuni flag riservati nell'intestazione gzip (ad esempio [FLG](http://www.zlib.org/rfc-gzip.html#header-trailer)) vengano impostati in base alla specifica. Ciò può causare un'eccezione nei punti in cui i valori in precedenza non validi venivano ignorati.</span><span class="sxs-lookup"><span data-stu-id="0174d-111">The native implementation enforces that values for some reserved flags inside the gzip header (i.e. [FLG](http://www.zlib.org/rfc-gzip.html#header-trailer)) are set according to the specification, which may cause it to throw an exception where previously invalid values were ignored.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0174d-112">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="0174d-112">Suggestion</span></span>

<span data-ttu-id="0174d-113">Se la decompressione con API native compromette il comportamento dell'app, è possibile rifiutare esplicitamente questa funzionalità aggiungendo l'opzione `Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression` alla sezione `runtime` del file app.config e impostandola su `true`:</span><span class="sxs-lookup"><span data-stu-id="0174d-113">If decompression with native APIs has adversely affected the behavior of your app, you can opt out of this feature by adding the `Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression` switch to the `runtime` section of your app.config file and setting it to `true`:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="0174d-114">Nome</span><span class="sxs-lookup"><span data-stu-id="0174d-114">Name</span></span>    | <span data-ttu-id="0174d-115">Valore</span><span class="sxs-lookup"><span data-stu-id="0174d-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0174d-116">Scope</span><span class="sxs-lookup"><span data-stu-id="0174d-116">Scope</span></span>   | <span data-ttu-id="0174d-117">Minorenne</span><span class="sxs-lookup"><span data-stu-id="0174d-117">Minor</span></span>       |
| <span data-ttu-id="0174d-118">Version</span><span class="sxs-lookup"><span data-stu-id="0174d-118">Version</span></span> | <span data-ttu-id="0174d-119">4.7.2</span><span class="sxs-lookup"><span data-stu-id="0174d-119">4.7.2</span></span>       |
| <span data-ttu-id="0174d-120">Type</span><span class="sxs-lookup"><span data-stu-id="0174d-120">Type</span></span>    | <span data-ttu-id="0174d-121">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="0174d-121">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="0174d-122">API interessate</span><span class="sxs-lookup"><span data-stu-id="0174d-122">Affected APIs</span></span>

- <xref:System.IO.Compression.DeflateStream?displayProperty=nameWithType>
- <xref:System.IO.Compression.GZipStream?displayProperty=nameWithType>
