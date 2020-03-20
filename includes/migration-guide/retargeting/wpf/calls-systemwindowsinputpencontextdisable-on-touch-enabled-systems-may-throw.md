---
ms.openlocfilehash: 6bb8c87af66e744514fb43e628c6423487342ac2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "72887788"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="dc549-101">Le chiamate a System.Windows.Input.PenContext.Disable nei sistemi abilitati per il tocco possono generare ArgumentException</span><span class="sxs-lookup"><span data-stu-id="dc549-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="dc549-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="dc549-102">Details</span></span>|<span data-ttu-id="dc549-103">In alcuni casi, le chiamate al metodo **System.Windows.Intput.PenContext.Disable** interno nei sistemi abilitati per il tocco possono generare una <code>T:System.ArgumentException</code> non gestita a causa della reentrancy.</span><span class="sxs-lookup"><span data-stu-id="dc549-103">Under some circumstances, calls to the internal **System.Windows.Intput.PenContext.Disable** method on touch-enabled systems may throw an unhandled <code>T:System.ArgumentException</code> because of reentrancy.</span></span>|
|<span data-ttu-id="dc549-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="dc549-104">Suggestion</span></span>|<span data-ttu-id="dc549-105">Questo problema è stato risolto in .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="dc549-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="dc549-106">Per evitare l'eccezione, eseguire l'aggiornamento a una versione di .NET Framework a partire da .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="dc549-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>|
|<span data-ttu-id="dc549-107">Scope</span><span class="sxs-lookup"><span data-stu-id="dc549-107">Scope</span></span>|<span data-ttu-id="dc549-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="dc549-108">Edge</span></span>|
|<span data-ttu-id="dc549-109">Versione</span><span class="sxs-lookup"><span data-stu-id="dc549-109">Version</span></span>|<span data-ttu-id="dc549-110">4.6.1</span><span class="sxs-lookup"><span data-stu-id="dc549-110">4.6.1</span></span>|
|<span data-ttu-id="dc549-111">Type</span><span class="sxs-lookup"><span data-stu-id="dc549-111">Type</span></span>|<span data-ttu-id="dc549-112">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="dc549-112">Retargeting</span></span>|
