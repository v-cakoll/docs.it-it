---
ms.openlocfilehash: 13d3799aeede86b01aa81ce1cd69b3c4c22311ca
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620482"
---
### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a><span data-ttu-id="df8bf-101">Il limite di annullamento predefinito per TextBox è 100</span><span class="sxs-lookup"><span data-stu-id="df8bf-101">WPF TextBox defaults to undo limit of 100</span></span>

#### <a name="details"></a><span data-ttu-id="df8bf-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="df8bf-102">Details</span></span>

<span data-ttu-id="df8bf-103">In .NET Framework 4.5 il limite di annullamento predefinito per una casella di testo WPF è 100, anziché essere illimitato come in .NET Framework 4.0</span><span class="sxs-lookup"><span data-stu-id="df8bf-103">In .NET Framework 4.5, the default undo limit for a WPF textbox is 100 (as opposed to being unlimited in .NET Framework 4.0)</span></span>

#### <a name="suggestion"></a><span data-ttu-id="df8bf-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="df8bf-104">Suggestion</span></span>

<span data-ttu-id="df8bf-105">Se un limite di annullamento di 100 è troppo basso, il limite può essere impostato in modo esplicito con <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit></span><span class="sxs-lookup"><span data-stu-id="df8bf-105">If an undo limit of 100 is too low, the limit can be set explicitly with <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit></span></span>

| <span data-ttu-id="df8bf-106">Nome</span><span class="sxs-lookup"><span data-stu-id="df8bf-106">Name</span></span>    | <span data-ttu-id="df8bf-107">Valore</span><span class="sxs-lookup"><span data-stu-id="df8bf-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="df8bf-108">Scope</span><span class="sxs-lookup"><span data-stu-id="df8bf-108">Scope</span></span>   |<span data-ttu-id="df8bf-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="df8bf-109">Edge</span></span>|
|<span data-ttu-id="df8bf-110">Version</span><span class="sxs-lookup"><span data-stu-id="df8bf-110">Version</span></span>|<span data-ttu-id="df8bf-111">4.5</span><span class="sxs-lookup"><span data-stu-id="df8bf-111">4.5</span></span>|
|<span data-ttu-id="df8bf-112">Type</span><span class="sxs-lookup"><span data-stu-id="df8bf-112">Type</span></span>|<span data-ttu-id="df8bf-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="df8bf-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="df8bf-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="df8bf-114">Affected APIs</span></span>

-<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
