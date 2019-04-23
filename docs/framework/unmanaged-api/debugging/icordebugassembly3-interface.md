---
title: Interfaccia ICorDebugAssembly3
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eecb135e034c3565e805ea776115579488b2a4d5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210308"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="131c9-102">Interfaccia ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="131c9-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="131c9-103">Estende logicamente l'interfaccia ICorDebugAssembly per fornire il supporto per l'assembly del contenitore e gli assembly contenuti.</span><span class="sxs-lookup"><span data-stu-id="131c9-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="131c9-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="131c9-104">Methods</span></span>  
  
|<span data-ttu-id="131c9-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="131c9-105">Method</span></span>|<span data-ttu-id="131c9-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="131c9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="131c9-107">Metodo EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="131c9-107">EnumerateContainedAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="131c9-108">Ottiene un enumeratore per gli assembly contenuti in questo assembly.</span><span class="sxs-lookup"><span data-stu-id="131c9-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="131c9-109">Metodo GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="131c9-109">GetContainerAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="131c9-110">Restituisce l'assembly del contenitore di questo oggetto `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="131c9-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="131c9-111">Note</span><span class="sxs-lookup"><span data-stu-id="131c9-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="131c9-112">L'interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="131c9-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="131c9-113">Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="131c9-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="131c9-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="131c9-114">Requirements</span></span>  
 <span data-ttu-id="131c9-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="131c9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="131c9-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="131c9-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="131c9-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="131c9-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="131c9-118">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="131c9-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="131c9-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="131c9-119">See also</span></span>

- [<span data-ttu-id="131c9-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="131c9-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="131c9-121">Debug</span><span class="sxs-lookup"><span data-stu-id="131c9-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
