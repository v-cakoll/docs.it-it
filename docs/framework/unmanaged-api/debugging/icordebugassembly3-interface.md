---
title: Interfaccia ICorDebugAssembly3
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e581b4256da2ecc19a8b97520e0e70fef972b549
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="a2e0c-102">Interfaccia ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="a2e0c-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="a2e0c-103">Estende logicamente l'interfaccia ICorDebugAssembly per fornire il supporto per l'assembly del contenitore e gli assembly contenuti.</span><span class="sxs-lookup"><span data-stu-id="a2e0c-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a2e0c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a2e0c-104">Methods</span></span>  
  
|<span data-ttu-id="a2e0c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a2e0c-105">Method</span></span>|<span data-ttu-id="a2e0c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a2e0c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a2e0c-107">Metodo EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="a2e0c-107">EnumerateContainedAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="a2e0c-108">Ottiene un enumeratore per gli assembly contenuti in questo assembly.</span><span class="sxs-lookup"><span data-stu-id="a2e0c-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="a2e0c-109">Metodo GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="a2e0c-109">GetContainerAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="a2e0c-110">Restituisce l'assembly del contenitore di questo oggetto `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="a2e0c-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2e0c-111">Note</span><span class="sxs-lookup"><span data-stu-id="a2e0c-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2e0c-112">L'interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a2e0c-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="a2e0c-113">Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a2e0c-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2e0c-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a2e0c-114">Requirements</span></span>  
 <span data-ttu-id="a2e0c-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2e0c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2e0c-116">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a2e0c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2e0c-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2e0c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2e0c-118">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2e0c-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2e0c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2e0c-119">See Also</span></span>  
 [<span data-ttu-id="a2e0c-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a2e0c-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="a2e0c-121">Debug</span><span class="sxs-lookup"><span data-stu-id="a2e0c-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
