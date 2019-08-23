---
title: Interfaccia ICorDebugAssembly3
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca77360c36ff2cdce7ee47d5c3883dd824c6cef8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959318"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="08c2e-102">Interfaccia ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="08c2e-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="08c2e-103">Estende logicamente l'interfaccia ICorDebugAssembly per fornire supporto per gli assembly contenitore e i relativi assembly contenuti.</span><span class="sxs-lookup"><span data-stu-id="08c2e-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="08c2e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="08c2e-104">Methods</span></span>  
  
|<span data-ttu-id="08c2e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="08c2e-105">Method</span></span>|<span data-ttu-id="08c2e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08c2e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="08c2e-107">Metodo EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="08c2e-107">EnumerateContainedAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="08c2e-108">Ottiene un enumeratore per gli assembly contenuti in questo assembly.</span><span class="sxs-lookup"><span data-stu-id="08c2e-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="08c2e-109">Metodo GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="08c2e-109">GetContainerAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="08c2e-110">Restituisce l'assembly del contenitore di questo oggetto `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="08c2e-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08c2e-111">Note</span><span class="sxs-lookup"><span data-stu-id="08c2e-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="08c2e-112">L'interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="08c2e-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="08c2e-113">Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="08c2e-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08c2e-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="08c2e-114">Requirements</span></span>  
 <span data-ttu-id="08c2e-115">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08c2e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08c2e-116">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="08c2e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08c2e-117">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08c2e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08c2e-118">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08c2e-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08c2e-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08c2e-119">See also</span></span>

- [<span data-ttu-id="08c2e-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="08c2e-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="08c2e-121">Debug</span><span class="sxs-lookup"><span data-stu-id="08c2e-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
