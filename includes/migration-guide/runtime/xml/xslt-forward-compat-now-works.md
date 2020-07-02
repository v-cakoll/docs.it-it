---
ms.openlocfilehash: e3b9711ac66901d69838de4c9f309d086b06fd4d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620518"
---
### <a name="xslt-forward-compat-now-works"></a><span data-ttu-id="3020d-101">La compatibilità con le versioni successive di XSLT ora funziona</span><span class="sxs-lookup"><span data-stu-id="3020d-101">XSLT forward compat now works</span></span>

#### <a name="details"></a><span data-ttu-id="3020d-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3020d-102">Details</span></span>

<span data-ttu-id="3020d-103">In .NET Framework 4 la compatibilità con le versioni successive di XSLT 1.0 presenta i seguenti problemi:</span><span class="sxs-lookup"><span data-stu-id="3020d-103">In the .NET Framework 4, XSLT 1.0 forward compatibility had the following issues:</span></span><ul><li><span data-ttu-id="3020d-104">Il caricamento di un foglio di stile ha avuto esito negativo se la versione è stata impostata su 2.0 e il parser ha incontrato un costrutto XSLT 1.0 sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="3020d-104">Loading a style sheet failed if its version was set to 2.0 and the parser encountered an unrecognized XSLT 1.0 construct.</span></span></li><li><span data-ttu-id="3020d-105">Il costrutto <code>xsl:sort</code> non è riuscito a ordinare i dati se la versione del foglio di stile era impostata su 1.1.</span><span class="sxs-lookup"><span data-stu-id="3020d-105">The <code>xsl:sort</code> construct failed to sort data if the style sheet version was set to 1.1.</span></span></li></ul><span data-ttu-id="3020d-106">In .NET Framework 4.5 questi problemi sono stati corretti e la modalità di compatibilità con le versioni successive di XSLT 1.0 funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="3020d-106">In the .NET Framework 4.5, these issues have been fixed, and XSLT 1.0 forward compatibility mode works properly.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3020d-107">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="3020d-107">Suggestion</span></span>

<span data-ttu-id="3020d-108">La maggior parte delle app non dovrebbe essere interessata, tuttavia i dati verranno ordinati in modo diverso in alcuni casi ora che viene rispettato il costrutto xsl:sort.</span><span class="sxs-lookup"><span data-stu-id="3020d-108">Most apps should be unaffected, however data will be sorted differently in some cases now that xsl:sort is respected.</span></span> <span data-ttu-id="3020d-109">Se si usa <code>xsl:sort</code> nei fogli di stile 1.1, verificare che le app non dipendano dall'ordine dei dati non ordinato.</span><span class="sxs-lookup"><span data-stu-id="3020d-109">If <code>xsl:sort</code> is used in 1.1 style sheets, confirm that apps were not depending on the unsorted order of data.</span></span> <span data-ttu-id="3020d-110">Se le app si basano sul comportamento di ordinamento della versione 4.0, rimuovere <code>xsl:sort</code> dal foglio di stile.</span><span class="sxs-lookup"><span data-stu-id="3020d-110">If apps rely on the 4.0 sorting behavior, remove <code>xsl:sort</code> from the style sheet.</span></span>

| <span data-ttu-id="3020d-111">Nome</span><span class="sxs-lookup"><span data-stu-id="3020d-111">Name</span></span>    | <span data-ttu-id="3020d-112">Valore</span><span class="sxs-lookup"><span data-stu-id="3020d-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3020d-113">Scope</span><span class="sxs-lookup"><span data-stu-id="3020d-113">Scope</span></span>   |<span data-ttu-id="3020d-114">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3020d-114">Edge</span></span>|
|<span data-ttu-id="3020d-115">Version</span><span class="sxs-lookup"><span data-stu-id="3020d-115">Version</span></span>|<span data-ttu-id="3020d-116">4.5</span><span class="sxs-lookup"><span data-stu-id="3020d-116">4.5</span></span>|
|<span data-ttu-id="3020d-117">Type</span><span class="sxs-lookup"><span data-stu-id="3020d-117">Type</span></span>|<span data-ttu-id="3020d-118">Runtime</span><span class="sxs-lookup"><span data-stu-id="3020d-118">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3020d-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="3020d-119">Affected APIs</span></span>

-<xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=nameWithType></li></ul>|
