---
title: Interfacce di hosting
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- interfaces [.NET Framework hosting]
- hosting interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], hosting
ms.assetid: cc64cb05-38da-418e-815a-daac8e8e26e5
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 46208d6db716f7e1e7a443d958c059b22f74c46f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="hosting-interfaces"></a><span data-ttu-id="da410-102">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="da410-102">Hosting Interfaces</span></span>
<span data-ttu-id="da410-103">In questa sezione vengono descritte le interfacce non gestite host consente di integrare common language runtime (CLR) nelle relative applicazioni.</span><span class="sxs-lookup"><span data-stu-id="da410-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span>  
  
 <span data-ttu-id="da410-104">Le interfacce di hosting di .NET Framework versione 2.0 sostituiscono le interfacce di .NET Framework versioni 1.0 e 1.1.</span><span class="sxs-lookup"><span data-stu-id="da410-104">The .NET Framework version 2.0 hosting interfaces supersede the .NET Framework version 1.0 and 1.1 interfaces.</span></span> <span data-ttu-id="da410-105">Esistono differenze significative tra i due set di interfacce.</span><span class="sxs-lookup"><span data-stu-id="da410-105">There are significant differences between the two sets of interfaces.</span></span> <span data-ttu-id="da410-106">Combinazione di essi potrebbero causare un comportamento imprevisto e non è consigliata.</span><span class="sxs-lookup"><span data-stu-id="da410-106">Mixing them could cause unexpected behavior and is not recommended.</span></span>  
  
 <span data-ttu-id="da410-107">Le versioni di .NET Framework 3.0 e 3.5 utilizzano le interfacce di hosting di .NET Framework versione 2.0 e non introducono funzionalità di hosting.</span><span class="sxs-lookup"><span data-stu-id="da410-107">The .NET Framework versions 3.0 and 3.5 use the .NET Framework version 2.0 hosting interfaces, and do not introduce any hosting features.</span></span>  
  
 <span data-ttu-id="da410-108">Il [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] interfacce di hosting sostituiscono le interfacce di .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="da410-108">The [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] hosting interfaces supersede the .NET Framework 2.0 interfaces.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="da410-109">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="da410-109">In This Section</span></span>  
 [<span data-ttu-id="da410-110">Interfacce di hosting CLR deprecate e coclassi</span><span class="sxs-lookup"><span data-stu-id="da410-110">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="da410-111">Descrive le interfacce di hosting introdotte in .NET Framework versioni 1.0 e 1.1.</span><span class="sxs-lookup"><span data-stu-id="da410-111">Describes the hosting interfaces introduced in the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="da410-112">Interfacce di hosting CLR</span><span class="sxs-lookup"><span data-stu-id="da410-112">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="da410-113">Descrive le interfacce di hosting introdotte in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="da410-113">Describes the hosting interfaces introduced in the .NET Framework version 2.0.</span></span>  
  
 [<span data-ttu-id="da410-114">Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5</span><span class="sxs-lookup"><span data-stu-id="da410-114">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="da410-115">Vengono descritte le interfacce di hosting introdotte nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da410-115">Describes the hosting interfaces introduced in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="da410-116">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="da410-116">Related Sections</span></span>  
 [<span data-ttu-id="da410-117">Coclassi di hosting</span><span class="sxs-lookup"><span data-stu-id="da410-117">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [<span data-ttu-id="da410-118">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="da410-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="da410-119">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="da410-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
  
 [<span data-ttu-id="da410-120">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="da410-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
  
 [<span data-ttu-id="da410-121">Hosting</span><span class="sxs-lookup"><span data-stu-id="da410-121">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
  
 [<span data-ttu-id="da410-122">Host di runtime</span><span class="sxs-lookup"><span data-stu-id="da410-122">Runtime Hosts</span></span>](http://msdn.microsoft.com/en-us/99d9246a-b994-4fe5-985c-8588d1d59998)
