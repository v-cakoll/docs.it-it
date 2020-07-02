---
ms.openlocfilehash: a44458484ea09c566defeabc9b604bd55d994e93
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617536"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="4d0ea-101">Le chiamate a System.Windows.Input.PenContext.Disable nei sistemi abilitati per il tocco possono generare ArgumentException</span><span class="sxs-lookup"><span data-stu-id="4d0ea-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

#### <a name="details"></a><span data-ttu-id="4d0ea-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4d0ea-102">Details</span></span>

<span data-ttu-id="4d0ea-103">In alcuni casi, le chiamate al metodo **System.Windows.Intput.PenContext.Disable** interno nei sistemi abilitati per il tocco possono generare una `T:System.ArgumentException` non gestita a causa della reentrancy.</span><span class="sxs-lookup"><span data-stu-id="4d0ea-103">Under some circumstances, calls to the internal **System.Windows.Intput.PenContext.Disable** method on touch-enabled systems may throw an unhandled `T:System.ArgumentException` because of reentrancy.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4d0ea-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="4d0ea-104">Suggestion</span></span>

<span data-ttu-id="4d0ea-105">Questo problema è stato risolto in .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="4d0ea-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="4d0ea-106">Per evitare l'eccezione, eseguire l'aggiornamento a una versione di .NET Framework a partire da .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="4d0ea-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>

| <span data-ttu-id="4d0ea-107">Nome</span><span class="sxs-lookup"><span data-stu-id="4d0ea-107">Name</span></span>    | <span data-ttu-id="4d0ea-108">Valore</span><span class="sxs-lookup"><span data-stu-id="4d0ea-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4d0ea-109">Scope</span><span class="sxs-lookup"><span data-stu-id="4d0ea-109">Scope</span></span>   | <span data-ttu-id="4d0ea-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="4d0ea-110">Edge</span></span>        |
| <span data-ttu-id="4d0ea-111">Version</span><span class="sxs-lookup"><span data-stu-id="4d0ea-111">Version</span></span> | <span data-ttu-id="4d0ea-112">4.6.1</span><span class="sxs-lookup"><span data-stu-id="4d0ea-112">4.6.1</span></span>       |
| <span data-ttu-id="4d0ea-113">Type</span><span class="sxs-lookup"><span data-stu-id="4d0ea-113">Type</span></span>    | <span data-ttu-id="4d0ea-114">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="4d0ea-114">Retargeting</span></span> |
