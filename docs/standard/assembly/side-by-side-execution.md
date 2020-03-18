---
title: Assembly ed esecuzione contemporanea di più versioni
ms.date: 08/20/2019
helpviewer_keywords:
- side-by-side execution [.NET Framework]
- assemblies [.NET Framework], side-by-side execution
ms.assetid: e42036ee-7590-47d1-b884-cc856e39bd5d
ms.openlocfilehash: 234efba66d87b520b54d6d113afcc4bba0bfe06a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73138646"
---
# <a name="assemblies-and-side-by-side-execution"></a><span data-ttu-id="6ee4b-102">Assembly ed esecuzione contemporanea di più versioni</span><span class="sxs-lookup"><span data-stu-id="6ee4b-102">Assemblies and side-by-side execution</span></span>

<span data-ttu-id="6ee4b-103">L'esecuzione contemporanea di diverse versioni è la capacità di archiviare ed eseguire più versioni di un'applicazione o di un componente sullo stesso computer.</span><span class="sxs-lookup"><span data-stu-id="6ee4b-103">Side-by-side execution is the ability to store and execute multiple versions of an application or component on the same computer.</span></span> <span data-ttu-id="6ee4b-104">Tale caratteristica consente di avere sullo stesso computer più versioni del runtime e più versioni delle applicazioni e dei componenti che utilizzano una versione del runtime.</span><span class="sxs-lookup"><span data-stu-id="6ee4b-104">This means that you can have multiple versions of the runtime, and multiple versions of applications and components that use a version of the runtime, on the same computer at the same time.</span></span> <span data-ttu-id="6ee4b-105">L'esecuzione contemporanea di diverse versioni offre un maggior controllo per definire a quale versione di un componente un'applicazione è associata, e quale sia la versione del runtime da essa utilizzata.</span><span class="sxs-lookup"><span data-stu-id="6ee4b-105">Side-by-side execution gives you more control over what versions of a component an application binds to, and more control over what version of the runtime an application uses.</span></span>  
  
<span data-ttu-id="6ee4b-106">Il supporto per l'archiviazione e l'esecuzione contemporanea di diverse versioni dello stesso assembly è parte integrante della denominazione con nome sicuro ed è incorporato nell'infrastruttura del runtime.</span><span class="sxs-lookup"><span data-stu-id="6ee4b-106">Support for side-by-side storage and execution of different versions of the same assembly is an integral part of strong naming and is built into the infrastructure of the runtime.</span></span> <span data-ttu-id="6ee4b-107">Poiché il numero di versione dell'assembly con nome sicuro è parte della relativa identità, il runtime può archiviare più versioni dello stesso assembly nella Global Assembly Cache e caricare tali assembly in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6ee4b-107">Because the strong-named assembly's version number is part of its identity, the runtime can store multiple versions of the same assembly in the global assembly cache and load those assemblies at run time.</span></span>  
  
<span data-ttu-id="6ee4b-108">Benché il runtime offra la possibilità di creare applicazioni predisposte all'esecuzione contemporanea di diverse versioni, questa non viene implementata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6ee4b-108">Although the runtime provides you with the ability to create side-by-side applications, side-by-side execution is not automatic.</span></span> <span data-ttu-id="6ee4b-109">Per ulteriori informazioni sulla creazione di applicazioni per l'esecuzione side-by-side, vedere Linee guida per la creazione di [componenti per l'esecuzione side-by-side](../../framework/deployment/guidelines-for-creating-components-for-side-by-side-execution.md).</span><span class="sxs-lookup"><span data-stu-id="6ee4b-109">For more information on creating applications for side-by-side execution, see [Guidelines for creating components for side-by-side execution](../../framework/deployment/guidelines-for-creating-components-for-side-by-side-execution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ee4b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ee4b-110">See also</span></span>

- [<span data-ttu-id="6ee4b-111">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="6ee4b-111">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="6ee4b-112">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="6ee4b-112">Assemblies in .NET</span></span>](index.md)
