---
ms.openlocfilehash: 395463225e3c1f1d168dd019ea75966ad54e5a8a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621259"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a><span data-ttu-id="4e1c2-101">La modifica della proprietà IsEnabled dell'elemento padre di un controllo TextBlock influisce sui controlli figlio</span><span class="sxs-lookup"><span data-stu-id="4e1c2-101">Changing the IsEnabled property of the parent of a TextBlock control affects any child controls</span></span>

#### <a name="details"></a><span data-ttu-id="4e1c2-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4e1c2-102">Details</span></span>

<span data-ttu-id="4e1c2-103">A partire da .NET Framework 4.6.2, la modifica della proprietà <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> dell'elemento padre di un controllo <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> influisce sui controlli figlio, ad esempio collegamenti ipertestuali e pulsanti, del controllo <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>. In .NET Framework 4.6.1 e versioni precedenti i controlli all'interno di <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> non sempre riflettono lo stato della proprietà <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> dell'elemento padre <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="4e1c2-103">Starting with the .NET Framework 4.6.2, changing the <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> property of the parent of a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control affects any child controls (such as hyperlinks and buttons) of the <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control.In the .NET Framework 4.6.1 and earlier versions, controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> did not always reflect the state of the <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> property of the <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> parent.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4e1c2-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="4e1c2-104">Suggestion</span></span>

<span data-ttu-id="4e1c2-105">No.</span><span class="sxs-lookup"><span data-stu-id="4e1c2-105">None.</span></span> <span data-ttu-id="4e1c2-106">Questa modifica è conforme al comportamento previsto per i controlli all'interno di un controllo <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="4e1c2-106">This change conforms to the expected behavior for controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control.</span></span>

| <span data-ttu-id="4e1c2-107">Nome</span><span class="sxs-lookup"><span data-stu-id="4e1c2-107">Name</span></span>    | <span data-ttu-id="4e1c2-108">Valore</span><span class="sxs-lookup"><span data-stu-id="4e1c2-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4e1c2-109">Scope</span><span class="sxs-lookup"><span data-stu-id="4e1c2-109">Scope</span></span>   |<span data-ttu-id="4e1c2-110">Minorenne</span><span class="sxs-lookup"><span data-stu-id="4e1c2-110">Minor</span></span>|
|<span data-ttu-id="4e1c2-111">Version</span><span class="sxs-lookup"><span data-stu-id="4e1c2-111">Version</span></span>|<span data-ttu-id="4e1c2-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="4e1c2-112">4.6.2</span></span>|
|<span data-ttu-id="4e1c2-113">Type</span><span class="sxs-lookup"><span data-stu-id="4e1c2-113">Type</span></span>|<span data-ttu-id="4e1c2-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="4e1c2-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4e1c2-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="4e1c2-115">Affected APIs</span></span>

-<xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType></li></ul>|
