---
ms.openlocfilehash: 6bb8c87af66e744514fb43e628c6423487342ac2
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72887788"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="47cab-101">Le chiamate a System.Windows.Input.PenContext.Disable nei sistemi abilitati per il tocco possono generare ArgumentException</span><span class="sxs-lookup"><span data-stu-id="47cab-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="47cab-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="47cab-102">Details</span></span>|<span data-ttu-id="47cab-103">In alcuni casi, le chiamate al metodo **System.Windows.Intput.PenContext.Disable** interno nei sistemi abilitati per il tocco possono generare una <code>T:System.ArgumentException</code> non gestita a causa della reentrancy.</span><span class="sxs-lookup"><span data-stu-id="47cab-103">Under some circumstances, calls to the internal **System.Windows.Intput.PenContext.Disable** method on touch-enabled systems may throw an unhandled <code>T:System.ArgumentException</code> because of reentrancy.</span></span>|
|<span data-ttu-id="47cab-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="47cab-104">Suggestion</span></span>|<span data-ttu-id="47cab-105">Questo problema è stato risolto in .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="47cab-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="47cab-106">Per evitare l'eccezione, eseguire l'aggiornamento a una versione di .NET Framework a partire da .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="47cab-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>|
|<span data-ttu-id="47cab-107">Scope</span><span class="sxs-lookup"><span data-stu-id="47cab-107">Scope</span></span>|<span data-ttu-id="47cab-108">Marginale</span><span class="sxs-lookup"><span data-stu-id="47cab-108">Edge</span></span>|
|<span data-ttu-id="47cab-109">Versione</span><span class="sxs-lookup"><span data-stu-id="47cab-109">Version</span></span>|<span data-ttu-id="47cab-110">4.6.1</span><span class="sxs-lookup"><span data-stu-id="47cab-110">4.6.1</span></span>|
|<span data-ttu-id="47cab-111">Digitare</span><span class="sxs-lookup"><span data-stu-id="47cab-111">Type</span></span>|<span data-ttu-id="47cab-112">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="47cab-112">Retargeting</span></span>|
