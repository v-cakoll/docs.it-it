---
title: Interfaccia ICorDebugSymbolProvider2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7666b8d64b689d3640594f07614be97b72e85a8f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="4c27c-102">Interfaccia ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="4c27c-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="4c27c-103">Estende logicamente il [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interfaccia per il recupero di informazioni sui simboli di debug aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="4c27c-103">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4c27c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="4c27c-104">Methods</span></span>  
  
|<span data-ttu-id="4c27c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="4c27c-105">Method</span></span>|<span data-ttu-id="4c27c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c27c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4c27c-107">Metodo GetTypeProps</span><span class="sxs-lookup"><span data-stu-id="4c27c-107">GetFrameProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="4c27c-108">Restituisce l'indirizzo RVA (Relative Virtual Address) iniziale di un metodo e il frame padre in base a un indirizzo virtuale relativo al codice.</span><span class="sxs-lookup"><span data-stu-id="4c27c-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="4c27c-109">Metodo GetGenericDictionaryInfo</span><span class="sxs-lookup"><span data-stu-id="4c27c-109">GetGenericDictionaryInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="4c27c-110">Recupera una mappa di dizionari generici.</span><span class="sxs-lookup"><span data-stu-id="4c27c-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c27c-111">Note</span><span class="sxs-lookup"><span data-stu-id="4c27c-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c27c-112">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4c27c-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="4c27c-113">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="4c27c-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c27c-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4c27c-114">Requirements</span></span>  
 <span data-ttu-id="4c27c-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c27c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c27c-116">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="4c27c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4c27c-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c27c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c27c-118">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c27c-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c27c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c27c-119">See Also</span></span>  
 [<span data-ttu-id="4c27c-120">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="4c27c-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="4c27c-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4c27c-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="4c27c-122">Debug</span><span class="sxs-lookup"><span data-stu-id="4c27c-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
