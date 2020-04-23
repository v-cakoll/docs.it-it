---
title: Utilizzo dei componenti serviti con la Global Assembly Cache
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- GAC (global assembly cache), serviced components
- serviced components, global assembly cache
- global assembly cache, serviced components
ms.assetid: 3423e5d9-234c-4571-8161-e35f6d130128
ms.openlocfilehash: 99627cb14088f037c58bfa1eec72bd4f88d06011
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119760"
---
# <a name="using-serviced-components-with-the-global-assembly-cache"></a><span data-ttu-id="bf6ae-102">Utilizzo dei componenti serviti con la Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="bf6ae-102">Using Serviced Components with the Global Assembly Cache</span></span>
<span data-ttu-id="bf6ae-103">È consigliabile inserire nella Global Assembly Cache i componenti serviti (componenti COM+ di codice gestito).</span><span class="sxs-lookup"><span data-stu-id="bf6ae-103">Serviced components (managed code COM+ components) should be put in the Global Assembly Cache.</span></span> <span data-ttu-id="bf6ae-104">In alcuni scenari, ma non in tutti, la gestione dei componenti serviti non inclusi nella Global Assembly Cache può essere eseguita da Common Language Runtime e dai servizi COM+.</span><span class="sxs-lookup"><span data-stu-id="bf6ae-104">In some scenarios, the Common Language Runtime and COM+ Services can handle serviced components that are not in the Global Assembly Cache; in other scenarios, they cannot.</span></span> <span data-ttu-id="bf6ae-105">Questo caso viene illustrato negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf6ae-105">The following scenarios illustrate this:</span></span>  
  
- <span data-ttu-id="bf6ae-106">Per quanto riguarda i componenti serviti di un'applicazione COM+ Server, è necessario che l'assembly contenente i componenti si trovi nella Global Assembly Cache, poiché Dllhost.exe non viene eseguito nella stessa directory in cui si trovano i componenti serviti.</span><span class="sxs-lookup"><span data-stu-id="bf6ae-106">For serviced components in a COM+ Server application, the assembly containing the components must be in the Global Assembly Cache, because Dllhost.exe does not run in the same directory as the one that contains the serviced components.</span></span>  
  
- <span data-ttu-id="bf6ae-107">Per quanto riguarda i componenti serviti di un'applicazione COM+ Library, Common Language Runtime e i servizi COM+ sono in grado di risolvere i riferimenti all'assembly contenente i componenti effettuando una ricerca nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="bf6ae-107">For serviced components in a COM+ Library application, the runtime and COM+ Services can resolve the reference to the assembly containing the components by searching in the current directory.</span></span> <span data-ttu-id="bf6ae-108">In questo caso non è quindi necessario che l'assembly si trovi nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="bf6ae-108">In this case, the assembly does not have to be in the global assembly cache.</span></span>  
  
- <span data-ttu-id="bf6ae-109">La situazione è diversa per i componenti serviti di un'applicazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="bf6ae-109">For serviced components in an ASP.NET application, the situation is different.</span></span> <span data-ttu-id="bf6ae-110">Se si inserisce l'assembly contenente i componenti serviti nella directory bin in cui risiede il codice base dell'applicazione e si usa la registrazione su richiesta, verrà effettuata la copia con shadowing dell'assembly nella Download Cache, poiché ASP.NET si avvale delle funzionalità di shadowing di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="bf6ae-110">If you place the assembly containing the serviced components in the bin directory of the application base and use on-demand registration, the assembly will be shadow-copied into the download cache because ASP.NET leverages the shadow capabilities of the runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf6ae-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf6ae-111">See also</span></span>

- [<span data-ttu-id="bf6ae-112">Uso di assembly e della Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="bf6ae-112">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="bf6ae-113">Gacutil. exe (strumento Global Assembly Cache)</span><span class="sxs-lookup"><span data-stu-id="bf6ae-113">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
