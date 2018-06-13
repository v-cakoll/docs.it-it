---
title: Interfaccia ICorDebugAssembly3
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5042f59b3716d077cc441585004e075b765c0cfb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407855"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="762eb-102">Interfaccia ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="762eb-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="762eb-103">Estende logicamente l'interfaccia ICorDebugAssembly per fornire il supporto per l'assembly del contenitore e gli assembly contenuti.</span><span class="sxs-lookup"><span data-stu-id="762eb-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="762eb-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="762eb-104">Methods</span></span>  
  
|<span data-ttu-id="762eb-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="762eb-105">Method</span></span>|<span data-ttu-id="762eb-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="762eb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="762eb-107">Metodo EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="762eb-107">EnumerateContainedAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="762eb-108">Ottiene un enumeratore per gli assembly contenuti in questo assembly.</span><span class="sxs-lookup"><span data-stu-id="762eb-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="762eb-109">Metodo GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="762eb-109">GetContainerAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="762eb-110">Restituisce l'assembly del contenitore di questo oggetto `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="762eb-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="762eb-111">Note</span><span class="sxs-lookup"><span data-stu-id="762eb-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="762eb-112">L'interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="762eb-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="762eb-113">Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="762eb-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="762eb-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="762eb-114">Requirements</span></span>  
 <span data-ttu-id="762eb-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="762eb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="762eb-116">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="762eb-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="762eb-117">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="762eb-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="762eb-118">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="762eb-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="762eb-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="762eb-119">See Also</span></span>  
 [<span data-ttu-id="762eb-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="762eb-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="762eb-121">Debug</span><span class="sxs-lookup"><span data-stu-id="762eb-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
