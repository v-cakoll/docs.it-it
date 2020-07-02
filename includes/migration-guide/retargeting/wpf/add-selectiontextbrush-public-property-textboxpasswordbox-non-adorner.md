---
ms.openlocfilehash: aade03c29ff16053a97683499cf719a98ae33f3f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616266"
---
### <a name="add-selectiontextbrush-public-property-to-textboxpasswordbox-non-adorner-selection"></a><span data-ttu-id="75e5a-101">Aggiungere la proprietà pubblica SelectionTextBrush alla selezione non basata su Adorner TextBox/PasswordBox</span><span class="sxs-lookup"><span data-stu-id="75e5a-101">Add SelectionTextBrush public property to TextBox/PasswordBox non-adorner selection</span></span>

#### <a name="details"></a><span data-ttu-id="75e5a-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="75e5a-102">Details</span></span>

<span data-ttu-id="75e5a-103">Nelle applicazioni WPF l'uso della [selezione testo non basata su Adorner](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-TextBox-PasswordBox-text-selection-does-not-follow-system-colors.md) per <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.PasswordBox> consente ora agli sviluppatori di impostare la nuova proprietà SelectionTextBrush per modificare il rendering del testo selezionato.</span><span class="sxs-lookup"><span data-stu-id="75e5a-103">In WPF applications using [non-adorner based text selection](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-TextBox-PasswordBox-text-selection-does-not-follow-system-colors.md) for <xref:System.Windows.Controls.TextBox> and <xref:System.Windows.Controls.PasswordBox>, developers may now set the newly added SelectionTextBrush property in order to alter the rendering of the selected text.</span></span>  <span data-ttu-id="75e5a-104">Per impostazione predefinita, questo colore viene modificato con <xref:System.Windows.SystemColors.HighlightTextBrushKey>.</span><span class="sxs-lookup"><span data-stu-id="75e5a-104">By default, this color changes with <xref:System.Windows.SystemColors.HighlightTextBrushKey>.</span></span>  <span data-ttu-id="75e5a-105">Se la selezione testo non basata su Adorner non è abilitata, questa proprietà non produce alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="75e5a-105">If non-adorner based text selection is not enabled, this property does nothing.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="75e5a-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="75e5a-106">Suggestion</span></span>

<span data-ttu-id="75e5a-107">Dopo che la selezione testo non basata su Adorner è stata abilitata, è possibile usare le proprietà <xref:System.Windows.Controls.PasswordBox.SelectionTextBrush?displayProperty=nameWithType> e <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush> per modificare l'aspetto del testo selezionato.</span><span class="sxs-lookup"><span data-stu-id="75e5a-107">Once non-adorner based text selection is enabled, you can use the <xref:System.Windows.Controls.PasswordBox.SelectionTextBrush?displayProperty=nameWithType> and <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush> property to change the appearance of the selected text.</span></span> <span data-ttu-id="75e5a-108">A tale scopo, usare XAML:</span><span class="sxs-lookup"><span data-stu-id="75e5a-108">This can be achieved using XAML:</span></span>

<pre><code class="lang-xaml">&lt;TextBox SelectionBrush=&quot;Red&quot; SelectionTextBrush=&quot;White&quot;  SelectionOpacity=&quot;0.5&quot;&#13;&#10;Foreground=&quot;Blue&quot; CaretBrush=&quot;Blue&quot;&gt;&#13;&#10;This is some text.&#13;&#10;&lt;/TextBox&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="75e5a-109">Nome</span><span class="sxs-lookup"><span data-stu-id="75e5a-109">Name</span></span>    | <span data-ttu-id="75e5a-110">Valore</span><span class="sxs-lookup"><span data-stu-id="75e5a-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="75e5a-111">Scope</span><span class="sxs-lookup"><span data-stu-id="75e5a-111">Scope</span></span>   | <span data-ttu-id="75e5a-112">Principale</span><span class="sxs-lookup"><span data-stu-id="75e5a-112">Major</span></span>       |
| <span data-ttu-id="75e5a-113">Version</span><span class="sxs-lookup"><span data-stu-id="75e5a-113">Version</span></span> | <span data-ttu-id="75e5a-114">4.8</span><span class="sxs-lookup"><span data-stu-id="75e5a-114">4.8</span></span>         |
| <span data-ttu-id="75e5a-115">Type</span><span class="sxs-lookup"><span data-stu-id="75e5a-115">Type</span></span>    | <span data-ttu-id="75e5a-116">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="75e5a-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="75e5a-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="75e5a-117">Affected APIs</span></span>

- <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrushProperty?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush?displayProperty=nameWithType>
- [<span data-ttu-id="75e5a-118">System.Windows.Controls.TextBox</span><span class="sxs-lookup"><span data-stu-id="75e5a-118">System.Windows.Controls.TextBox</span></span>](xref:System.Windows.Controls.TextBox)
- [<span data-ttu-id="75e5a-119">System.Windows.Controls.PasswordBox</span><span class="sxs-lookup"><span data-stu-id="75e5a-119">System.Windows.Controls.PasswordBox</span></span>](xref:System.Windows.Controls.PasswordBox)
