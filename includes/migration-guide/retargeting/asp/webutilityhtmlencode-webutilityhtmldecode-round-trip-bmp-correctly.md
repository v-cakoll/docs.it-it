---
ms.openlocfilehash: acb5b467fc8f0692d8fa1b3b8263fd27308cc124
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617165"
---
### <a name="webutilityhtmlencode-and-webutilityhtmldecode-round-trip-bmp-correctly"></a><span data-ttu-id="7df7d-101">Round trip corretto di WebUtility.HtmlEncode e WebUtility.HtmlDecode per BMP</span><span class="sxs-lookup"><span data-stu-id="7df7d-101">WebUtility.HtmlEncode and WebUtility.HtmlDecode round-trip BMP correctly</span></span>

#### <a name="details"></a><span data-ttu-id="7df7d-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="7df7d-102">Details</span></span>

<span data-ttu-id="7df7d-103">Per le applicazioni destinate a .NET Framework 4.5, i caratteri al di fuori del piano di base multilinguistico (BMP, Basic Multilingual Plane) eseguono correttamente il round trip quando vengono passati ai metodi <xref:System.Net.WebUtility.HtmlDecode(System.String)>.</span><span class="sxs-lookup"><span data-stu-id="7df7d-103">For applications that target the .NET Framework 4.5, characters that are outside the Basic Multilingual Plane (BMP) round-trip correctly when they are passed to the <xref:System.Net.WebUtility.HtmlDecode(System.String)> methods.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7df7d-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="7df7d-104">Suggestion</span></span>

<span data-ttu-id="7df7d-105">Questa modifica non dovrebbe avere alcun effetto sulle applicazioni correnti, ma per ripristinare il comportamento originale, impostare l' `targetFramework` attributo dell' `<httpRuntime>` elemento su una stringa diversa da "4,5".</span><span class="sxs-lookup"><span data-stu-id="7df7d-105">This change should have no effect on current applications, but to restore the original behavior, set the `targetFramework` attribute of the `<httpRuntime>` element to a string other than "4.5".</span></span> <span data-ttu-id="7df7d-106">È inoltre possibile impostare gli attributi `unicodeEncodingConformance` e `unicodeDecodingConformance` dell'elemento di configurazione `<webUtility>` per controllare questo comportamento indipendentemente dalla versione di destinazione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7df7d-106">You can also set the `unicodeEncodingConformance` and `unicodeDecodingConformance` attributes of the `<webUtility>` configuration element to control this behavior independently of the targeted version of the .NET Framework.</span></span>

| <span data-ttu-id="7df7d-107">Nome</span><span class="sxs-lookup"><span data-stu-id="7df7d-107">Name</span></span>    | <span data-ttu-id="7df7d-108">Valore</span><span class="sxs-lookup"><span data-stu-id="7df7d-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7df7d-109">Scope</span><span class="sxs-lookup"><span data-stu-id="7df7d-109">Scope</span></span>   | <span data-ttu-id="7df7d-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7df7d-110">Edge</span></span>        |
| <span data-ttu-id="7df7d-111">Version</span><span class="sxs-lookup"><span data-stu-id="7df7d-111">Version</span></span> | <span data-ttu-id="7df7d-112">4.5</span><span class="sxs-lookup"><span data-stu-id="7df7d-112">4.5</span></span>         |
| <span data-ttu-id="7df7d-113">Type</span><span class="sxs-lookup"><span data-stu-id="7df7d-113">Type</span></span>    | <span data-ttu-id="7df7d-114">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="7df7d-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="7df7d-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="7df7d-115">Affected APIs</span></span>

- <xref:System.Net.WebUtility.HtmlEncode(System.String)?displayProperty=nameWithType>
- <xref:System.Net.WebUtility.HtmlEncode(System.String,System.IO.TextWriter)?displayProperty=nameWithType>
