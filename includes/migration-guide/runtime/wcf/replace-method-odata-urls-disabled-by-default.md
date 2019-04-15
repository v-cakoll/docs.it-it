---
ms.openlocfilehash: 6dc3669433804a4524c18d5a932f9879343ab508
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235456"
---
### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a><span data-ttu-id="ad024-101">Il metodo Replace negli URL OData è disabilitato per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="ad024-101">The Replace method in OData URLs is disabled by default</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ad024-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ad024-102">Details</span></span>|<span data-ttu-id="ad024-103">A partire da .NET Framework 4.5, il metodo Replace negli URL OData è disabilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ad024-103">Beginning in the .NET Framework 4.5, the Replace method in OData URLs is disabled by default.</span></span> <span data-ttu-id="ad024-104">Quando il metodo Replace è disabilitato per OData, ora per impostazione predefinita, le eventuali richieste utente che includono funzioni di sostituzione (non comuni) avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="ad024-104">When OData Replace is disabled (now by default), any user requests including replace functions (which are uncommon) will fail.</span></span>|
|<span data-ttu-id="ad024-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="ad024-105">Suggestion</span></span>|<span data-ttu-id="ad024-106">Se il metodo Replace è necessario (situazione non comune) è possibile riabilitarlo tramite le impostazioni di configurazione (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=name>).</span><span class="sxs-lookup"><span data-stu-id="ad024-106">If the replace method is required (which is uncommon), it can be re-enabled through a config settings (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=name>).</span></span> <span data-ttu-id="ad024-107">L'abilitazione di un metodo Replace, tuttavia, può introdurre vulnerabilità per la sicurezza ed è consigliabile usarlo solo dopo attente valutazioni.</span><span class="sxs-lookup"><span data-stu-id="ad024-107">However, an enabled replace method can open security vulnerabilities and should only be used after careful review.</span></span>|
|<span data-ttu-id="ad024-108">Ambito</span><span class="sxs-lookup"><span data-stu-id="ad024-108">Scope</span></span>|<span data-ttu-id="ad024-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ad024-109">Edge</span></span>|
|<span data-ttu-id="ad024-110">Versione</span><span class="sxs-lookup"><span data-stu-id="ad024-110">Version</span></span>|<span data-ttu-id="ad024-111">4.5</span><span class="sxs-lookup"><span data-stu-id="ad024-111">4.5</span></span>|
|<span data-ttu-id="ad024-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="ad024-112">Type</span></span>|<span data-ttu-id="ad024-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="ad024-113">Runtime</span></span>|
|<span data-ttu-id="ad024-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="ad024-114">Affected APIs</span></span>|<ul><li><xref:System.Data.Services.DataService%601?displayProperty=nameWithType></li></ul>|
