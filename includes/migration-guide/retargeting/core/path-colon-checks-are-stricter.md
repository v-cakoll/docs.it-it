---
ms.openlocfilehash: 3e4a5936bbac4e77efc5f7e68b55ddf49bae5d43
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614481"
---
### <a name="path-colon-checks-are-stricter"></a><span data-ttu-id="55cbc-101">I controlli della presenza di due punti nel percorso sono più severi</span><span class="sxs-lookup"><span data-stu-id="55cbc-101">Path colon checks are stricter</span></span>

#### <a name="details"></a><span data-ttu-id="55cbc-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="55cbc-102">Details</span></span>

<span data-ttu-id="55cbc-103">In .NET Framework 4.6.2 sono state apportate varie modifiche per supportare i percorsi in precedenza non supportati (sia per lunghezza che per formato).</span><span class="sxs-lookup"><span data-stu-id="55cbc-103">In .NET Framework 4.6.2, a number of changes were made to support previously unsupported paths (both in length and format).</span></span> <span data-ttu-id="55cbc-104">I controlli della sintassi corretta del separatore appropriato per le unità (due punti) sono ora più corretti. L'effetto collaterale è però il blocco di alcuni percorsi URI in un gruppo selezionato di API Path in cui l'uso era tollerato.</span><span class="sxs-lookup"><span data-stu-id="55cbc-104">Checks for proper drive separator (colon) syntax were made more correct, which had the side effect of blocking some URI paths in a few select Path APIs where they used to be tolerated.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="55cbc-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="55cbc-105">Suggestion</span></span>

<span data-ttu-id="55cbc-106">Per il passaggio di un URI alle API interessate, modificare prima di tutto la stringa in modo che sia un percorso valido.</span><span class="sxs-lookup"><span data-stu-id="55cbc-106">If passing a URI to affected APIs, modify the string to be a legal path first.</span></span><ul><li><span data-ttu-id="55cbc-107">Rimuovere manualmente lo schema dagli URL (ad esempio rimuovere `file://` dagli URL)</span><span class="sxs-lookup"><span data-stu-id="55cbc-107">Remove the scheme from URLs manually (e.g. remove `file://` from URLs)</span></span>

- <span data-ttu-id="55cbc-108">Passare l'URI alla classe <xref:System.Uri> e usare <xref:System.Uri.LocalPath></span><span class="sxs-lookup"><span data-stu-id="55cbc-108">Pass the URI to the <xref:System.Uri> class and use <xref:System.Uri.LocalPath></span></span>

<span data-ttu-id="55cbc-109">In alternativa, è possibile rifiutare esplicitamente la nuova normalizzazione dei percorsi impostando l'opzione di AppContext `Switch.System.IO.UseLegacyPathHandling` su true.</span><span class="sxs-lookup"><span data-stu-id="55cbc-109">Alternatively, you can opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling` AppContext switch to true.</span></span>

| <span data-ttu-id="55cbc-110">Nome</span><span class="sxs-lookup"><span data-stu-id="55cbc-110">Name</span></span>    | <span data-ttu-id="55cbc-111">Valore</span><span class="sxs-lookup"><span data-stu-id="55cbc-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="55cbc-112">Scope</span><span class="sxs-lookup"><span data-stu-id="55cbc-112">Scope</span></span>   | <span data-ttu-id="55cbc-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="55cbc-113">Edge</span></span>        |
| <span data-ttu-id="55cbc-114">Version</span><span class="sxs-lookup"><span data-stu-id="55cbc-114">Version</span></span> | <span data-ttu-id="55cbc-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="55cbc-115">4.6.2</span></span>       |
| <span data-ttu-id="55cbc-116">Type</span><span class="sxs-lookup"><span data-stu-id="55cbc-116">Type</span></span>    | <span data-ttu-id="55cbc-117">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="55cbc-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="55cbc-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="55cbc-118">Affected APIs</span></span>

- <xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType>
- <xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType>
