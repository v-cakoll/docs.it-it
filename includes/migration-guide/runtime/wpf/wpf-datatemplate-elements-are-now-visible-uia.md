---
ms.openlocfilehash: 06c699281c8890ac65be1d282b72b54774acc280
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620473"
---
### <a name="wpf-datatemplate-elements-are-now-visible-to-uia"></a><span data-ttu-id="6f5ab-101">Gli elementi WPF DataTemplate ora sono visibili per Automazione interfaccia utente (UIA)</span><span class="sxs-lookup"><span data-stu-id="6f5ab-101">WPF DataTemplate elements are now visible to UIA</span></span>

#### <a name="details"></a><span data-ttu-id="6f5ab-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6f5ab-102">Details</span></span>

<span data-ttu-id="6f5ab-103">In precedenza gli elementi <xref:System.Windows.DataTemplate?displayProperty=fullName> erano invisibili per Automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="6f5ab-103">Previously, <xref:System.Windows.DataTemplate?displayProperty=fullName> elements were invisible to UI Automation.</span></span> <span data-ttu-id="6f5ab-104">A partire dalla versione 4.5, Automazione interfaccia utente rileva questi elementi.</span><span class="sxs-lookup"><span data-stu-id="6f5ab-104">Beginning in 4.5, UI Automation will detect these elements.</span></span> <span data-ttu-id="6f5ab-105">Questo è utile in molti casi, ma può causare problemi per i test che dipendono da alberi di automazione interfaccia utente che non contengono elementi <xref:System.Windows.DataTemplate?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="6f5ab-105">This is useful in many cases, but can break tests that depend on UIA trees not containing <xref:System.Windows.DataTemplate?displayProperty=fullName> elements.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6f5ab-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="6f5ab-106">Suggestion</span></span>

<span data-ttu-id="6f5ab-107">Potrebbe essere necessario aggiornare i test di Automazione interfaccia utente per questa app per tenere conto dell'albero di Automazione interfaccia utente che ora include elementi <xref:System.Windows.DataTemplate?displayProperty=fullName> precedentemente invisibili.</span><span class="sxs-lookup"><span data-stu-id="6f5ab-107">UI Automation tests for this app may need updated to account for the UIA tree now including previously invisible <xref:System.Windows.DataTemplate?displayProperty=fullName> elements.</span></span> <span data-ttu-id="6f5ab-108">Ad esempio, nei test che prevedono che alcuni elementi siano adiacenti può essere ora necessario prevedere che possono infrapporsi elementi di Automazione interfaccia utente precedentemente invisibili.</span><span class="sxs-lookup"><span data-stu-id="6f5ab-108">For example, tests that expect some elements to be next to each other may now need to expect previously invisible UIA elements in between.</span></span> <span data-ttu-id="6f5ab-109">Oppure, potrebbe essere necessario aggiornare con nuovi valori i test che si basano su conteggi o indici specifici per gli elementi di Automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="6f5ab-109">Or tests that rely on certain counts or indexes for UIA elements may need updated with new values.</span></span>

| <span data-ttu-id="6f5ab-110">Nome</span><span class="sxs-lookup"><span data-stu-id="6f5ab-110">Name</span></span>    | <span data-ttu-id="6f5ab-111">Valore</span><span class="sxs-lookup"><span data-stu-id="6f5ab-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6f5ab-112">Scope</span><span class="sxs-lookup"><span data-stu-id="6f5ab-112">Scope</span></span>   |<span data-ttu-id="6f5ab-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6f5ab-113">Edge</span></span>|
|<span data-ttu-id="6f5ab-114">Version</span><span class="sxs-lookup"><span data-stu-id="6f5ab-114">Version</span></span>|<span data-ttu-id="6f5ab-115">4.5</span><span class="sxs-lookup"><span data-stu-id="6f5ab-115">4.5</span></span>|
|<span data-ttu-id="6f5ab-116">Type</span><span class="sxs-lookup"><span data-stu-id="6f5ab-116">Type</span></span>|<span data-ttu-id="6f5ab-117">Runtime</span><span class="sxs-lookup"><span data-stu-id="6f5ab-117">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6f5ab-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="6f5ab-118">Affected APIs</span></span>

-<xref:System.Windows.DataTemplate.%23ctor></li><li><xref:System.Windows.DataTemplate.%23ctor(System.Object)></li></ul>|
