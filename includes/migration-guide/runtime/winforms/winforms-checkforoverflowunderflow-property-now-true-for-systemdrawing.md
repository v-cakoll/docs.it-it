---
ms.openlocfilehash: 8b2a01eb6dfdd5bd2bcbef6014d4edeb3ec82ac1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235561"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a><span data-ttu-id="87b54-101">La proprietà CheckForOverflowUnderflow di WinForm ora è true per System.Drawing</span><span class="sxs-lookup"><span data-stu-id="87b54-101">WinForm's CheckForOverflowUnderflow property is now true for System.Drawing</span></span>

|   |   |
|---|---|
|<span data-ttu-id="87b54-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="87b54-102">Details</span></span>|<span data-ttu-id="87b54-103">La proprietà CheckForOverflowUnderflow per l'assembly System.Drawing.dll è impostata su true.</span><span class="sxs-lookup"><span data-stu-id="87b54-103">The CheckForOverflowUnderflow property for the System.Drawing.dll assembly is set to true.</span></span>|
|<span data-ttu-id="87b54-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="87b54-104">Suggestion</span></span>|<span data-ttu-id="87b54-105">In precedenza, quando si verificavano overflow, il risultato veniva automaticamente troncato.</span><span class="sxs-lookup"><span data-stu-id="87b54-105">Previously when overflows occurred, the result would be silently truncated.</span></span> <span data-ttu-id="87b54-106">Ora viene generata un'eccezione <xref:System.OverflowException?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="87b54-106">Now an <xref:System.OverflowException?displayProperty=name> exception is thrown.</span></span>|
|<span data-ttu-id="87b54-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="87b54-107">Scope</span></span>|<span data-ttu-id="87b54-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="87b54-108">Edge</span></span>|
|<span data-ttu-id="87b54-109">Versione</span><span class="sxs-lookup"><span data-stu-id="87b54-109">Version</span></span>|<span data-ttu-id="87b54-110">4.5</span><span class="sxs-lookup"><span data-stu-id="87b54-110">4.5</span></span>|
|<span data-ttu-id="87b54-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="87b54-111">Type</span></span>|<span data-ttu-id="87b54-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="87b54-112">Runtime</span></span>|
