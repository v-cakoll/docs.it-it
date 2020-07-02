---
ms.openlocfilehash: d0de1a262d57c67dd4dfb258d5ac013af5d8783d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617231"
---
### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a><span data-ttu-id="1dafc-101">TextBox.Text di WPF può non essere sincronizzata con il data binding</span><span class="sxs-lookup"><span data-stu-id="1dafc-101">WPF TextBox.Text can be out-of-sync with databinding</span></span>

#### <a name="details"></a><span data-ttu-id="1dafc-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1dafc-102">Details</span></span>

<span data-ttu-id="1dafc-103">In alcuni casi, la proprietà <xref:System.Windows.Controls.TextBox.Text> riflette un valore precedente del valore della proprietà associata a dati se viene modificata durante un'operazione di scrittura di associazione dati.</span><span class="sxs-lookup"><span data-stu-id="1dafc-103">In some cases, the <xref:System.Windows.Controls.TextBox.Text> property reflects a previous value of the databound property value if the property is modified during a databinding write operation.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1dafc-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="1dafc-104">Suggestion</span></span>

<span data-ttu-id="1dafc-105">Non dovrebbe avere alcun impatto negativo.</span><span class="sxs-lookup"><span data-stu-id="1dafc-105">This should have no negative impact.</span></span> <span data-ttu-id="1dafc-106">Tuttavia, è possibile ripristinare il comportamento precedente impostando la proprietà <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> su `false`.</span><span class="sxs-lookup"><span data-stu-id="1dafc-106">However, you can restore the previous behavior by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> property to `false`.</span></span>

| <span data-ttu-id="1dafc-107">Nome</span><span class="sxs-lookup"><span data-stu-id="1dafc-107">Name</span></span>    | <span data-ttu-id="1dafc-108">Valore</span><span class="sxs-lookup"><span data-stu-id="1dafc-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1dafc-109">Scope</span><span class="sxs-lookup"><span data-stu-id="1dafc-109">Scope</span></span>   | <span data-ttu-id="1dafc-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1dafc-110">Edge</span></span>        |
| <span data-ttu-id="1dafc-111">Version</span><span class="sxs-lookup"><span data-stu-id="1dafc-111">Version</span></span> | <span data-ttu-id="1dafc-112">4.5</span><span class="sxs-lookup"><span data-stu-id="1dafc-112">4.5</span></span>         |
|<span data-ttu-id="1dafc-113">Type</span><span class="sxs-lookup"><span data-stu-id="1dafc-113">Type</span></span>|<span data-ttu-id="1dafc-114">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="1dafc-114">Retargeting</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1dafc-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="1dafc-115">Affected APIs</span></span>

- <xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType>
