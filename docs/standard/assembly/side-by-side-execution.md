---
title: Assembly ed esecuzione contemporanea di più versioni
description: Informazioni sull'esecuzione side-by-Side, ovvero la possibilità di archiviare ed eseguire più versioni di un'applicazione o di un componente nello stesso computer.
ms.date: 08/20/2019
helpviewer_keywords:
- side-by-side execution [.NET Framework]
- assemblies [.NET Framework], side-by-side execution
ms.assetid: e42036ee-7590-47d1-b884-cc856e39bd5d
ms.openlocfilehash: 74b5710c7e8ad60873fb83a3699ce3992ead6e07
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378635"
---
# <a name="assemblies-and-side-by-side-execution"></a><span data-ttu-id="7a674-103">Assembly ed esecuzione contemporanea di più versioni</span><span class="sxs-lookup"><span data-stu-id="7a674-103">Assemblies and side-by-side execution</span></span>

<span data-ttu-id="7a674-104">L'esecuzione contemporanea di diverse versioni è la capacità di archiviare ed eseguire più versioni di un'applicazione o di un componente sullo stesso computer.</span><span class="sxs-lookup"><span data-stu-id="7a674-104">Side-by-side execution is the ability to store and execute multiple versions of an application or component on the same computer.</span></span> <span data-ttu-id="7a674-105">Tale caratteristica consente di avere sullo stesso computer più versioni del runtime e più versioni delle applicazioni e dei componenti che utilizzano una versione del runtime.</span><span class="sxs-lookup"><span data-stu-id="7a674-105">This means that you can have multiple versions of the runtime, and multiple versions of applications and components that use a version of the runtime, on the same computer at the same time.</span></span> <span data-ttu-id="7a674-106">L'esecuzione contemporanea di diverse versioni offre un maggior controllo per definire a quale versione di un componente un'applicazione è associata, e quale sia la versione del runtime da essa utilizzata.</span><span class="sxs-lookup"><span data-stu-id="7a674-106">Side-by-side execution gives you more control over what versions of a component an application binds to, and more control over what version of the runtime an application uses.</span></span>  
  
<span data-ttu-id="7a674-107">Il supporto per l'archiviazione e l'esecuzione contemporanea di diverse versioni dello stesso assembly è parte integrante della denominazione con nome sicuro ed è incorporato nell'infrastruttura del runtime.</span><span class="sxs-lookup"><span data-stu-id="7a674-107">Support for side-by-side storage and execution of different versions of the same assembly is an integral part of strong naming and is built into the infrastructure of the runtime.</span></span> <span data-ttu-id="7a674-108">Poiché il numero di versione dell'assembly con nome sicuro è parte della relativa identità, il runtime può archiviare più versioni dello stesso assembly nella Global Assembly Cache e caricare tali assembly in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7a674-108">Because the strong-named assembly's version number is part of its identity, the runtime can store multiple versions of the same assembly in the global assembly cache and load those assemblies at run time.</span></span>  
  
<span data-ttu-id="7a674-109">Benché il runtime offra la possibilità di creare applicazioni predisposte all'esecuzione contemporanea di diverse versioni, questa non viene implementata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7a674-109">Although the runtime provides you with the ability to create side-by-side applications, side-by-side execution is not automatic.</span></span> <span data-ttu-id="7a674-110">Per ulteriori informazioni sulla creazione di applicazioni per l'esecuzione side-by-Side, vedere [linee guida per la creazione di componenti per l'esecuzione side-by-side](../../framework/deployment/guidelines-for-creating-components-for-side-by-side-execution.md).</span><span class="sxs-lookup"><span data-stu-id="7a674-110">For more information on creating applications for side-by-side execution, see [Guidelines for creating components for side-by-side execution](../../framework/deployment/guidelines-for-creating-components-for-side-by-side-execution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a674-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a674-111">See also</span></span>

- [<span data-ttu-id="7a674-112">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="7a674-112">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="7a674-113">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="7a674-113">Assemblies in .NET</span></span>](index.md)
