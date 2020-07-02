---
ms.openlocfilehash: b2fcacdb02c411c4dcb12051bf0c6759faccdea2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620391"
---
### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a><span data-ttu-id="52355-101">Il metodo Replace negli URL OData è disabilitato per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="52355-101">The Replace method in OData URLs is disabled by default</span></span>

#### <a name="details"></a><span data-ttu-id="52355-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="52355-102">Details</span></span>

<span data-ttu-id="52355-103">A partire da .NET Framework 4.5, il metodo Replace negli URL OData è disabilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="52355-103">Beginning in the .NET Framework 4.5, the Replace method in OData URLs is disabled by default.</span></span> <span data-ttu-id="52355-104">Quando il metodo Replace è disabilitato per OData, ora per impostazione predefinita, le eventuali richieste utente che includono funzioni di sostituzione (non comuni) avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="52355-104">When OData Replace is disabled (now by default), any user requests including replace functions (which are uncommon) will fail.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="52355-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="52355-105">Suggestion</span></span>

<span data-ttu-id="52355-106">Se il metodo Replace è necessario (situazione non comune) è possibile riabilitarlo tramite le impostazioni di configurazione (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=fullName>).</span><span class="sxs-lookup"><span data-stu-id="52355-106">If the replace method is required (which is uncommon), it can be re-enabled through a config settings (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=fullName>).</span></span> <span data-ttu-id="52355-107">L'abilitazione di un metodo Replace, tuttavia, può introdurre vulnerabilità per la sicurezza ed è consigliabile usarlo solo dopo attente valutazioni.</span><span class="sxs-lookup"><span data-stu-id="52355-107">However, an enabled replace method can open security vulnerabilities and should only be used after careful review.</span></span>

| <span data-ttu-id="52355-108">Nome</span><span class="sxs-lookup"><span data-stu-id="52355-108">Name</span></span>    | <span data-ttu-id="52355-109">Valore</span><span class="sxs-lookup"><span data-stu-id="52355-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="52355-110">Scope</span><span class="sxs-lookup"><span data-stu-id="52355-110">Scope</span></span>   |<span data-ttu-id="52355-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="52355-111">Edge</span></span>|
|<span data-ttu-id="52355-112">Version</span><span class="sxs-lookup"><span data-stu-id="52355-112">Version</span></span>|<span data-ttu-id="52355-113">4.5</span><span class="sxs-lookup"><span data-stu-id="52355-113">4.5</span></span>|
|<span data-ttu-id="52355-114">Type</span><span class="sxs-lookup"><span data-stu-id="52355-114">Type</span></span>|<span data-ttu-id="52355-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="52355-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="52355-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="52355-116">Affected APIs</span></span>

-<xref:System.Data.Services.DataService%601?displayProperty=nameWithType></li></ul>|
