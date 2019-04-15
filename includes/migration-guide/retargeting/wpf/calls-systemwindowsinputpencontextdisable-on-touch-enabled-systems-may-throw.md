---
ms.openlocfilehash: 3cd5052dffcb059c240a310e0b89384f28409264
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234463"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="d2690-101">Le chiamate a System.Windows.Input.PenContext.Disable nei sistemi abilitati per il tocco possono generare ArgumentException</span><span class="sxs-lookup"><span data-stu-id="d2690-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d2690-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d2690-102">Details</span></span>|<span data-ttu-id="d2690-103">In alcuni casi, le chiamate al metodo <strong>System.Windows.Intput.PenContext.Disable</strong> interno nei sistemi abilitati per il tocco possono generare una <code>T:System.ArgumentException</code> non gestita a causa della reentrancy.</span><span class="sxs-lookup"><span data-stu-id="d2690-103">Under some circumstances, calls to the internal <strong>System.Windows.Intput.PenContext.Disable</strong> method on touch-enabled systems may throw an unhandled <code>T:System.ArgumentException</code> because of reentrancy.</span></span>|
|<span data-ttu-id="d2690-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="d2690-104">Suggestion</span></span>|<span data-ttu-id="d2690-105">Questo problema è stato risolto in .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="d2690-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="d2690-106">Per evitare l'eccezione, eseguire l'aggiornamento a una versione di .NET Framework a partire da .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="d2690-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>|
|<span data-ttu-id="d2690-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="d2690-107">Scope</span></span>|<span data-ttu-id="d2690-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d2690-108">Edge</span></span>|
|<span data-ttu-id="d2690-109">Versione</span><span class="sxs-lookup"><span data-stu-id="d2690-109">Version</span></span>|<span data-ttu-id="d2690-110">4.6.1</span><span class="sxs-lookup"><span data-stu-id="d2690-110">4.6.1</span></span>|
|<span data-ttu-id="d2690-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="d2690-111">Type</span></span>|<span data-ttu-id="d2690-112">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="d2690-112">Retargeting</span></span>|
