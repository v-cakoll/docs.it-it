---
ms.openlocfilehash: 8b0617d8f021a9534289fd7ae8539cd054684862
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234686"
---
### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a><span data-ttu-id="6e99c-101">TextBox.Text di WPF può non essere sincronizzata con il data binding</span><span class="sxs-lookup"><span data-stu-id="6e99c-101">WPF TextBox.Text can be out-of-sync with databinding</span></span>

|   |   |
|---|---|
|<span data-ttu-id="6e99c-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6e99c-102">Details</span></span>|<span data-ttu-id="6e99c-103">In alcuni casi, la proprietà <xref:System.Windows.Controls.TextBox.Text> riflette un valore precedente del valore della proprietà associata a dati se viene modificata durante un'operazione di scrittura di associazione dati.</span><span class="sxs-lookup"><span data-stu-id="6e99c-103">In some cases, the <xref:System.Windows.Controls.TextBox.Text> property reflects a previous value of the databound property value if the property is modified during a databinding write operation.</span></span>|
|<span data-ttu-id="6e99c-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="6e99c-104">Suggestion</span></span>|<span data-ttu-id="6e99c-105">Non dovrebbe avere alcun impatto negativo.</span><span class="sxs-lookup"><span data-stu-id="6e99c-105">This should have no negative impact.</span></span> <span data-ttu-id="6e99c-106">Tuttavia, è possibile ripristinare il comportamento precedente impostando la proprietà <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> su <code>false</code>.</span><span class="sxs-lookup"><span data-stu-id="6e99c-106">However, you can restore the previous behavior by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> property to <code>false</code>.</span></span>|
|<span data-ttu-id="6e99c-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="6e99c-107">Scope</span></span>|<span data-ttu-id="6e99c-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6e99c-108">Edge</span></span>|
|<span data-ttu-id="6e99c-109">Versione</span><span class="sxs-lookup"><span data-stu-id="6e99c-109">Version</span></span>|<span data-ttu-id="6e99c-110">4.5</span><span class="sxs-lookup"><span data-stu-id="6e99c-110">4.5</span></span>|
|<span data-ttu-id="6e99c-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="6e99c-111">Type</span></span>|<span data-ttu-id="6e99c-112">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="6e99c-112">Retargeting</span></span>|
|<span data-ttu-id="6e99c-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="6e99c-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType></li></ul>|
