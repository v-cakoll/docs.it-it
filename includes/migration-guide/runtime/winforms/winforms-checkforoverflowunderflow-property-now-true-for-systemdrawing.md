---
ms.openlocfilehash: 8b2a01eb6dfdd5bd2bcbef6014d4edeb3ec82ac1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804278"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a><span data-ttu-id="b9244-101">La proprietà CheckForOverflowUnderflow di WinForm ora è true per System.Drawing</span><span class="sxs-lookup"><span data-stu-id="b9244-101">WinForm's CheckForOverflowUnderflow property is now true for System.Drawing</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b9244-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b9244-102">Details</span></span>|<span data-ttu-id="b9244-103">La proprietà CheckForOverflowUnderflow per l'assembly System.Drawing.dll è impostata su true.</span><span class="sxs-lookup"><span data-stu-id="b9244-103">The CheckForOverflowUnderflow property for the System.Drawing.dll assembly is set to true.</span></span>|
|<span data-ttu-id="b9244-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="b9244-104">Suggestion</span></span>|<span data-ttu-id="b9244-105">In precedenza, quando si verificavano overflow, il risultato veniva automaticamente troncato.</span><span class="sxs-lookup"><span data-stu-id="b9244-105">Previously when overflows occurred, the result would be silently truncated.</span></span> <span data-ttu-id="b9244-106">Ora viene generata un'eccezione <xref:System.OverflowException?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="b9244-106">Now an <xref:System.OverflowException?displayProperty=name> exception is thrown.</span></span>|
|<span data-ttu-id="b9244-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="b9244-107">Scope</span></span>|<span data-ttu-id="b9244-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b9244-108">Edge</span></span>|
|<span data-ttu-id="b9244-109">Versione</span><span class="sxs-lookup"><span data-stu-id="b9244-109">Version</span></span>|<span data-ttu-id="b9244-110">4.5</span><span class="sxs-lookup"><span data-stu-id="b9244-110">4.5</span></span>|
|<span data-ttu-id="b9244-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="b9244-111">Type</span></span>|<span data-ttu-id="b9244-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="b9244-112">Runtime</span></span>|
