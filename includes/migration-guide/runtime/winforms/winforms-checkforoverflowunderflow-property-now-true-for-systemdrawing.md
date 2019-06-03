---
ms.openlocfilehash: 8b2a01eb6dfdd5bd2bcbef6014d4edeb3ec82ac1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379635"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a><span data-ttu-id="b566b-101">La proprietà CheckForOverflowUnderflow di WinForm ora è true per System.Drawing</span><span class="sxs-lookup"><span data-stu-id="b566b-101">WinForm's CheckForOverflowUnderflow property is now true for System.Drawing</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b566b-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b566b-102">Details</span></span>|<span data-ttu-id="b566b-103">La proprietà CheckForOverflowUnderflow per l'assembly System.Drawing.dll è impostata su true.</span><span class="sxs-lookup"><span data-stu-id="b566b-103">The CheckForOverflowUnderflow property for the System.Drawing.dll assembly is set to true.</span></span>|
|<span data-ttu-id="b566b-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="b566b-104">Suggestion</span></span>|<span data-ttu-id="b566b-105">In precedenza, quando si verificavano overflow, il risultato veniva automaticamente troncato.</span><span class="sxs-lookup"><span data-stu-id="b566b-105">Previously when overflows occurred, the result would be silently truncated.</span></span> <span data-ttu-id="b566b-106">Ora viene generata un'eccezione <xref:System.OverflowException?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="b566b-106">Now an <xref:System.OverflowException?displayProperty=name> exception is thrown.</span></span>|
|<span data-ttu-id="b566b-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="b566b-107">Scope</span></span>|<span data-ttu-id="b566b-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b566b-108">Edge</span></span>|
|<span data-ttu-id="b566b-109">Versione</span><span class="sxs-lookup"><span data-stu-id="b566b-109">Version</span></span>|<span data-ttu-id="b566b-110">4.5</span><span class="sxs-lookup"><span data-stu-id="b566b-110">4.5</span></span>|
|<span data-ttu-id="b566b-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="b566b-111">Type</span></span>|<span data-ttu-id="b566b-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="b566b-112">Runtime</span></span>|
