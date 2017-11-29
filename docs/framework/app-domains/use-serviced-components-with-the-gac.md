---
title: Utilizzo dei componenti serviti con la Global Assembly Cache
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- GAC (global assembly cache), serviced components
- serviced components, global assembly cache
- global assembly cache, serviced components
ms.assetid: 3423e5d9-234c-4571-8161-e35f6d130128
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 45fd02c4f87d33766741e6fd023f9b40b9964d63
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="using-serviced-components-with-the-global-assembly-cache"></a><span data-ttu-id="57c84-102">Utilizzo dei componenti serviti con la Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="57c84-102">Using Serviced Components with the Global Assembly Cache</span></span>
<span data-ttu-id="57c84-103">È consigliabile inserire nella Global Assembly Cache i componenti serviti (componenti COM+ di codice gestito).</span><span class="sxs-lookup"><span data-stu-id="57c84-103">Serviced components (managed code COM+ components) should be put in the global assembly cache.</span></span> <span data-ttu-id="57c84-104">In alcuni scenari, ma non in tutti, la gestione dei componenti serviti non inclusi nella Global Assembly Cache può essere eseguita da Common Language Runtime e dai servizi COM+.</span><span class="sxs-lookup"><span data-stu-id="57c84-104">In some scenarios, the common language runtime and COM+ Services can handle serviced components that are not in the global assembly cache; in other scenarios, they cannot.</span></span> <span data-ttu-id="57c84-105">Questo caso viene illustrato negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="57c84-105">The following scenarios illustrate this:</span></span>  
  
-   <span data-ttu-id="57c84-106">Per quanto riguarda i componenti serviti di un'applicazione COM+ Server, è necessario che l'assembly contenente i componenti si trovi nella Global Assembly Cache, poiché Dllhost.exe non viene eseguito nella stessa directory in cui si trovano i componenti serviti.</span><span class="sxs-lookup"><span data-stu-id="57c84-106">For serviced components in a COM+ Server application, the assembly containing the components must be in the global assembly cache, because Dllhost.exe does not run in the same directory as the one that contains the serviced components.</span></span>  
  
-   <span data-ttu-id="57c84-107">Per quanto riguarda i componenti serviti di un'applicazione COM+ Library, Common Language Runtime e i servizi COM+ sono in grado di risolvere i riferimenti all'assembly contenente i componenti effettuando una ricerca nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="57c84-107">For serviced components in a COM+ Library application, the runtime and COM+ Services can resolve the reference to the assembly containing the components by searching in the current directory.</span></span> <span data-ttu-id="57c84-108">In questo caso non è quindi necessario che l'assembly si trovi nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="57c84-108">In this case, the assembly does not have to be in the global assembly cache.</span></span>  
  
-   <span data-ttu-id="57c84-109">La situazione è diversa per i componenti serviti di un'applicazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="57c84-109">For serviced components in an ASP.NET application, the situation is different.</span></span> <span data-ttu-id="57c84-110">Se si inserisce l'assembly contenente i componenti serviti nella directory bin in cui risiede il codice base dell'applicazione e si usa la registrazione su richiesta, verrà effettuata la copia con shadowing dell'assembly nella Download Cache, poiché ASP.NET si avvale delle funzionalità di shadowing di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="57c84-110">If you place the assembly containing the serviced components in the bin directory of the application base and use on-demand registration, the assembly will be shadow-copied into the download cache because ASP.NET leverages the shadow capabilities of the runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57c84-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57c84-111">See Also</span></span>  
 [<span data-ttu-id="57c84-112">Uso di assembly e della Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="57c84-112">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="57c84-113">Gacutil.exe (strumento Global Assembly Cache)</span><span class="sxs-lookup"><span data-stu-id="57c84-113">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
