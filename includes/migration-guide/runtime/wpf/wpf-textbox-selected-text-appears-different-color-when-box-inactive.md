---
ms.openlocfilehash: cd59818fe674e10a206725bea8a74c4aceed99b1
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620470"
---
### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a><span data-ttu-id="ae140-101">Il testo selezionato nel controllo TextBox WPF viene visualizzato con un colore diverso quando la casella di testo è inattiva</span><span class="sxs-lookup"><span data-stu-id="ae140-101">WPF TextBox selected text appears a different color when the text box is inactive</span></span>

#### <a name="details"></a><span data-ttu-id="ae140-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ae140-102">Details</span></span>

<span data-ttu-id="ae140-103">In .NET Framework 4.5, se una casella di testo WPF è inattiva (non ha lo stato attivo), il testo selezionato nella casella verrà visualizzato con un colore diverso rispetto a quando il controllo è attivo.</span><span class="sxs-lookup"><span data-stu-id="ae140-103">In .NET Framework 4.5, when a WPF text box control is inactive (it doesn't have focus), the selected text inside the box will appear a different color than when the control is active.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ae140-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="ae140-104">Suggestion</span></span>

<span data-ttu-id="ae140-105">È possibile ripristinare il comportamento precedente di .NET Framework 4.0 impostando la proprietà <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> su <code>false</code>.</span><span class="sxs-lookup"><span data-stu-id="ae140-105">The previous (.NET Framework 4.0) behavior may be restored by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> property to <code>false</code>.</span></span>

| <span data-ttu-id="ae140-106">Nome</span><span class="sxs-lookup"><span data-stu-id="ae140-106">Name</span></span>    | <span data-ttu-id="ae140-107">Valore</span><span class="sxs-lookup"><span data-stu-id="ae140-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ae140-108">Scope</span><span class="sxs-lookup"><span data-stu-id="ae140-108">Scope</span></span>   |<span data-ttu-id="ae140-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ae140-109">Edge</span></span>|
|<span data-ttu-id="ae140-110">Version</span><span class="sxs-lookup"><span data-stu-id="ae140-110">Version</span></span>|<span data-ttu-id="ae140-111">4.5</span><span class="sxs-lookup"><span data-stu-id="ae140-111">4.5</span></span>|
|<span data-ttu-id="ae140-112">Type</span><span class="sxs-lookup"><span data-stu-id="ae140-112">Type</span></span>|<span data-ttu-id="ae140-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="ae140-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ae140-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="ae140-114">Affected APIs</span></span>

-<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
