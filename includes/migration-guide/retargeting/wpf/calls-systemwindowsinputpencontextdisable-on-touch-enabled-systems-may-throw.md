---
ms.openlocfilehash: 0778285ef1b5702bd79743038a1bd21ba04612d6
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804353"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="0ff7b-101">Le chiamate a System.Windows.Input.PenContext.Disable nei sistemi abilitati per il tocco possono generare ArgumentException</span><span class="sxs-lookup"><span data-stu-id="0ff7b-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0ff7b-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0ff7b-102">Details</span></span>|<span data-ttu-id="0ff7b-103">In alcuni casi, le chiamate al metodo <strong>System.Windows.Intput.PenContext.Disable</strong> interno nei sistemi abilitati per il tocco possono generare una <code>T:System.ArgumentException</code> non gestita a causa della reentrancy.</span><span class="sxs-lookup"><span data-stu-id="0ff7b-103">Under some circumstances, calls to the internal <strong>System.Windows.Intput.PenContext.Disable</strong> method on touch-enabled systems may throw an unhandled <code>T:System.ArgumentException</code> because of reentrancy.</span></span>|
|<span data-ttu-id="0ff7b-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="0ff7b-104">Suggestion</span></span>|<span data-ttu-id="0ff7b-105">Questo problema è stato risolto in .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="0ff7b-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="0ff7b-106">Per evitare l'eccezione, eseguire l'aggiornamento a una versione di .NET Framework a partire da .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="0ff7b-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>|
|<span data-ttu-id="0ff7b-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="0ff7b-107">Scope</span></span>|<span data-ttu-id="0ff7b-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0ff7b-108">Edge</span></span>|
|<span data-ttu-id="0ff7b-109">Versione</span><span class="sxs-lookup"><span data-stu-id="0ff7b-109">Version</span></span>|<span data-ttu-id="0ff7b-110">4.6.1</span><span class="sxs-lookup"><span data-stu-id="0ff7b-110">4.6.1</span></span>|
|<span data-ttu-id="0ff7b-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="0ff7b-111">Type</span></span>|<span data-ttu-id="0ff7b-112">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="0ff7b-112">Retargeting</span></span>|

