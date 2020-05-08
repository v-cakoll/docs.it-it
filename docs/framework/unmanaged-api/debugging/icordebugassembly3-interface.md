---
title: Interfaccia ICorDebugAssembly3
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
ms.openlocfilehash: 67707092c80b0e07aa284336c426aba09ff991af
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894821"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="06fcf-102">Interfaccia ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="06fcf-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="06fcf-103">Estende logicamente l'interfaccia ICorDebugAssembly per fornire supporto per l'assembly del contenitore e per gli assembly contenuti.</span><span class="sxs-lookup"><span data-stu-id="06fcf-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="06fcf-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="06fcf-104">Methods</span></span>  
  
|<span data-ttu-id="06fcf-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="06fcf-105">Method</span></span>|<span data-ttu-id="06fcf-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="06fcf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="06fcf-107">Metodo EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="06fcf-107">EnumerateContainedAssemblies Method</span></span>](icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="06fcf-108">Ottiene un enumeratore per gli assembly contenuti in questo assembly.</span><span class="sxs-lookup"><span data-stu-id="06fcf-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="06fcf-109">Metodo GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="06fcf-109">GetContainerAssembly Method</span></span>](icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="06fcf-110">Restituisce l'assembly del contenitore di questo oggetto `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="06fcf-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06fcf-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="06fcf-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="06fcf-112">L'interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="06fcf-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="06fcf-113">Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="06fcf-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06fcf-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="06fcf-114">Requirements</span></span>  
 <span data-ttu-id="06fcf-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06fcf-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06fcf-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06fcf-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06fcf-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06fcf-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06fcf-118">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06fcf-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06fcf-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06fcf-119">See also</span></span>

- [<span data-ttu-id="06fcf-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="06fcf-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="06fcf-121">Debug</span><span class="sxs-lookup"><span data-stu-id="06fcf-121">Debugging</span></span>](index.md)
