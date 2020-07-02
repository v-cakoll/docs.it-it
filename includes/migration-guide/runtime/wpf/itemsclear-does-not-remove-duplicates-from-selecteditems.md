---
ms.openlocfilehash: 75f176133697056bab9349ba1d18d7a0e1aa7da2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620128"
---
### <a name="itemsclear-does-not-remove-duplicates-from-selecteditems"></a><span data-ttu-id="f8c95-101">Items.Clear non rimuove i duplicati da SelectedItems</span><span class="sxs-lookup"><span data-stu-id="f8c95-101">Items.Clear does not remove duplicates from SelectedItems</span></span>

#### <a name="details"></a><span data-ttu-id="f8c95-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f8c95-102">Details</span></span>

<span data-ttu-id="f8c95-103">Se un selettore con selezione multipla abilitata contiene duplicati nella raccolta <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>, lo stesso elemento viene visualizzato più volte.</span><span class="sxs-lookup"><span data-stu-id="f8c95-103">Suppose a Selector (with multiple selection enabled) has duplicates in its <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> collection - the same item appears more than once.</span></span>  <span data-ttu-id="f8c95-104">L'eliminazione di questi elementi dall'origine dati (ad esempio, chiamando Items.Clear) non li rimuove da <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>; viene rimossa solo la prima istanza.</span><span class="sxs-lookup"><span data-stu-id="f8c95-104">Removing those items from the data source (e.g. by calling Items.Clear) fails to remove them from <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>; only the first instance is removed.</span></span> <span data-ttu-id="f8c95-105">Nell'uso successivo di <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>, ad esempio SelectedItems.Clear(), si possono inoltre verificare errori, ad esempio <xref:System.ArgumentException?displayProperty=fullName>, in quanto <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> contiene elementi che non sono più nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="f8c95-105">Furthermore, subsequent use of <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> (e.g. SelectedItems.Clear()) can encounter problems such as <xref:System.ArgumentException?displayProperty=fullName>, because <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> contains items that are no longer in the data source.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f8c95-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="f8c95-106">Suggestion</span></span>

<span data-ttu-id="f8c95-107">Se possibile, eseguire l'aggiornamento a .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="f8c95-107">Upgrade if possible to .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="f8c95-108">Nome</span><span class="sxs-lookup"><span data-stu-id="f8c95-108">Name</span></span>    | <span data-ttu-id="f8c95-109">Valore</span><span class="sxs-lookup"><span data-stu-id="f8c95-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f8c95-110">Scope</span><span class="sxs-lookup"><span data-stu-id="f8c95-110">Scope</span></span>   |<span data-ttu-id="f8c95-111">Minorenne</span><span class="sxs-lookup"><span data-stu-id="f8c95-111">Minor</span></span>|
|<span data-ttu-id="f8c95-112">Version</span><span class="sxs-lookup"><span data-stu-id="f8c95-112">Version</span></span>|<span data-ttu-id="f8c95-113">4.5</span><span class="sxs-lookup"><span data-stu-id="f8c95-113">4.5</span></span>|
|<span data-ttu-id="f8c95-114">Type</span><span class="sxs-lookup"><span data-stu-id="f8c95-114">Type</span></span>|<span data-ttu-id="f8c95-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="f8c95-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f8c95-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="f8c95-116">Affected APIs</span></span>

-<xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=nameWithType></li></ul>|
