---
title: Interfaccia ICorDebugAssembly3
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eecb135e034c3565e805ea776115579488b2a4d5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645461"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="23148-102">Interfaccia ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="23148-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="23148-103">Estende logicamente l'interfaccia ICorDebugAssembly per fornire il supporto per l'assembly del contenitore e gli assembly contenuti.</span><span class="sxs-lookup"><span data-stu-id="23148-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="23148-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="23148-104">Methods</span></span>  
  
|<span data-ttu-id="23148-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="23148-105">Method</span></span>|<span data-ttu-id="23148-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23148-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="23148-107">Metodo EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="23148-107">EnumerateContainedAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="23148-108">Ottiene un enumeratore per gli assembly contenuti in questo assembly.</span><span class="sxs-lookup"><span data-stu-id="23148-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="23148-109">Metodo GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="23148-109">GetContainerAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="23148-110">Restituisce l'assembly del contenitore di questo oggetto `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="23148-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23148-111">Note</span><span class="sxs-lookup"><span data-stu-id="23148-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="23148-112">L'interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="23148-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="23148-113">Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="23148-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23148-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="23148-114">Requirements</span></span>  
 <span data-ttu-id="23148-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23148-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23148-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23148-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23148-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23148-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23148-118">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23148-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23148-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23148-119">See also</span></span>

- [<span data-ttu-id="23148-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="23148-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="23148-121">Debug</span><span class="sxs-lookup"><span data-stu-id="23148-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
