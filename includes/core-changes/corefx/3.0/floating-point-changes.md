---
ms.openlocfilehash: 22dbb1e982f83687a9e0eb288ed72c78c676db77
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021681"
---
### <a name="floating-point-formatting-and-parsing-behavior-changed"></a><span data-ttu-id="f3014-101">Modifiche al comportamento di formattazione e analisi a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="f3014-101">Floating-point formatting and parsing behavior changed</span></span>

<span data-ttu-id="f3014-102">Il comportamento di analisi e formattazione a virgola mobile (da parte dei <xref:System.Double> tipi e) <xref:System.Single> sono ora compatibili con IEEE.</span><span class="sxs-lookup"><span data-stu-id="f3014-102">Floating point parsing and formatting behavior (by the <xref:System.Double> and <xref:System.Single> types) are now IEEE-compliant.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f3014-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="f3014-103">Change description</span></span>

<span data-ttu-id="f3014-104">In .NET Core 2.2 e <xref:System.Double.ToString%2A?displayProperty=nameWithType> versioni <xref:System.Single.ToString%2A?displayProperty=nameWithType>precedenti la formattazione <xref:System.Single.Parse%2A?displayProperty=nameWithType>con <xref:System.Single.TryParse%2A?displayProperty=nameWithType> e , e l'analisi con <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, e non sono compatibili con IEEE.</span><span class="sxs-lookup"><span data-stu-id="f3014-104">In .NET Core 2.2 and earlier versions, formatting with <xref:System.Double.ToString%2A?displayProperty=nameWithType> and <xref:System.Single.ToString%2A?displayProperty=nameWithType>, and parsing with <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, <xref:System.Single.Parse%2A?displayProperty=nameWithType>, and <xref:System.Single.TryParse%2A?displayProperty=nameWithType> are not IEEE-compliant.</span></span> <span data-ttu-id="f3014-105">Di conseguenza, è impossibile garantire che un valore verrà eseguito il roundtrip con qualsiasi stringa di formato standard o personalizzata supportata.</span><span class="sxs-lookup"><span data-stu-id="f3014-105">As a result, it is impossible to guarantee that a value will roundtrip with any supported standard or custom format string.</span></span> <span data-ttu-id="f3014-106">Per alcuni input, il tentativo di analizzare un valore formattato può avere esito negativo e, per altri, il valore analizzato non è uguale al valore originale.</span><span class="sxs-lookup"><span data-stu-id="f3014-106">For some inputs, the attempt to parse a formatted value can fail, and for others, the parsed value doesn't equal the original value.</span></span>

<span data-ttu-id="f3014-107">A partire da .NET Core 3.0, le operazioni di analisi e formattazione sono compatibili con IEEE 754.</span><span class="sxs-lookup"><span data-stu-id="f3014-107">Starting with .NET Core 3.0, parsing and formatting operations are IEEE 754-compliant.</span></span> <span data-ttu-id="f3014-108">In questo modo si garantisce che il comportamento dei tipi a virgola mobile in .NET corrisponda a quello dei linguaggi compatibili con IEEE, ad esempio il linguaggio C.</span><span class="sxs-lookup"><span data-stu-id="f3014-108">This ensures that the behavior of floating-point types in .NET matches that of IEEE-compliant languages such as C#.</span></span> <span data-ttu-id="f3014-109">Per altre informazioni, vedere i miglioramenti di analisi e formattazione a virgola mobile nel post di blog di .NET Core 3.0.For more information, see the [Floating-point parsing and formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post.</span><span class="sxs-lookup"><span data-stu-id="f3014-109">For more information, see the [Floating-point parsing and formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f3014-110">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="f3014-110">Version introduced</span></span>

<span data-ttu-id="f3014-111">3.0</span><span class="sxs-lookup"><span data-stu-id="f3014-111">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f3014-112">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="f3014-112">Recommended action</span></span>

<span data-ttu-id="f3014-113">La sezione "Potenziale impatto sul codice esistente" del post di accanalisi e formattazione a virgola mobile nel post di blog [di .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) suggerisce modifiche al codice se si osserva una modifica del comportamento rispetto alle applicazioni .NET Core 2.2 In genere, ciò comporta l'utilizzo di una stringa di formato standard o personalizzata diversa per applicare il comportamento desiderato.</span><span class="sxs-lookup"><span data-stu-id="f3014-113">The "Potential impact to existing code" section of the [Floating-point parsing and formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post suggests changes to your code if you observe a change of behavior when compared to .NET Core 2.2 applications Generally, this involves using a different standard or custom format string to enforce the desired behavior.</span></span> <span data-ttu-id="f3014-114">Alcuni risultati potrebbero non avere una soluzione alternativa se in precedenza non erano corretti.</span><span class="sxs-lookup"><span data-stu-id="f3014-114">Some results may not have a workaround if they were previously incorrect.</span></span>

#### <a name="category"></a><span data-ttu-id="f3014-115">Category</span><span class="sxs-lookup"><span data-stu-id="f3014-115">Category</span></span>

<span data-ttu-id="f3014-116">Librerie .NET di base</span><span class="sxs-lookup"><span data-stu-id="f3014-116">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f3014-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="f3014-117">Affected APIs</span></span>

- <xref:System.Double.ToString%2A?displayProperty=nameWithType>
- <xref:System.Single.ToString%2A?displayProperty=nameWithType>
- <xref:System.Double.Parse%2A?displayProperty=nameWithType>
- <xref:System.Double.TryParse%2A?displayProperty=nameWithType>
- <xref:System.Single.Parse%2A?displayProperty=nameWithType>
- <xref:System.Single.TryParse%2A?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `Overload:System.Double.ToString`
- `Overload:System.Single.ToString`
- `Overload:System.Double.Parse`
- `Overload:System.Double.TryParse`
- `Overload:System.Single.Parse`
- `Overload:System.Single.TryParse`

-->
