---
ms.openlocfilehash: 4cd06fd02fadbaa9f74e40f850e688ee883454ed
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620446"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a><span data-ttu-id="b0c67-101">La proprietà CheckForOverflowUnderflow di WinForm ora è true per System.Drawing</span><span class="sxs-lookup"><span data-stu-id="b0c67-101">WinForm's CheckForOverflowUnderflow property is now true for System.Drawing</span></span>

#### <a name="details"></a><span data-ttu-id="b0c67-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b0c67-102">Details</span></span>

<span data-ttu-id="b0c67-103">La proprietà CheckForOverflowUnderflow per l'assembly System.Drawing.dll è impostata su true.</span><span class="sxs-lookup"><span data-stu-id="b0c67-103">The CheckForOverflowUnderflow property for the System.Drawing.dll assembly is set to true.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b0c67-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="b0c67-104">Suggestion</span></span>

<span data-ttu-id="b0c67-105">In precedenza, quando si verificavano overflow, il risultato veniva automaticamente troncato.</span><span class="sxs-lookup"><span data-stu-id="b0c67-105">Previously when overflows occurred, the result would be silently truncated.</span></span> <span data-ttu-id="b0c67-106">Ora viene generata un'eccezione <xref:System.OverflowException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="b0c67-106">Now an <xref:System.OverflowException?displayProperty=fullName> exception is thrown.</span></span>

| <span data-ttu-id="b0c67-107">Nome</span><span class="sxs-lookup"><span data-stu-id="b0c67-107">Name</span></span>    | <span data-ttu-id="b0c67-108">Valore</span><span class="sxs-lookup"><span data-stu-id="b0c67-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b0c67-109">Scope</span><span class="sxs-lookup"><span data-stu-id="b0c67-109">Scope</span></span>   |<span data-ttu-id="b0c67-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b0c67-110">Edge</span></span>|
|<span data-ttu-id="b0c67-111">Version</span><span class="sxs-lookup"><span data-stu-id="b0c67-111">Version</span></span>|<span data-ttu-id="b0c67-112">4.5</span><span class="sxs-lookup"><span data-stu-id="b0c67-112">4.5</span></span>|
|<span data-ttu-id="b0c67-113">Type</span><span class="sxs-lookup"><span data-stu-id="b0c67-113">Type</span></span>|<span data-ttu-id="b0c67-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="b0c67-114">Runtime</span></span>|
