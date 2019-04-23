---
title: Metodo ICorDebugAssembly3::GetContainerAssembly
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9bd4cd44eca9b12ab8773fd75b6262579cfe8e8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206083"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a><span data-ttu-id="52220-102">Metodo ICorDebugAssembly3::GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="52220-102">ICorDebugAssembly3::GetContainerAssembly Method</span></span>
<span data-ttu-id="52220-103">Restituisce l'assembly del contenitore di questo oggetto `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="52220-103">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52220-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="52220-104">Syntax</span></span>  
  
```  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52220-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="52220-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="52220-106">Un puntatore all'indirizzo di un oggetto ICorDebugAssembly che rappresenta l'assembly del contenitore, oppure **null** se la chiamata al metodo ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="52220-106">A pointer to the address of an ICorDebugAssembly object that represents the container assembly, or **null** if the method call fails.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52220-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="52220-107">Return Value</span></span>  
 <span data-ttu-id="52220-108">`S_OK` Se la chiamata al metodo ha esito positivo; in caso contrario, `S_FALSE`, e `ppAssembly` viene **null**.</span><span class="sxs-lookup"><span data-stu-id="52220-108">`S_OK` if the method call succeeds; otherwise, `S_FALSE`, and `ppAssembly` is **null**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52220-109">Note</span><span class="sxs-lookup"><span data-stu-id="52220-109">Remarks</span></span>  
 <span data-ttu-id="52220-110">Se l'assembly è stato unito ad altri assembly in un singolo assembly del contenitore, il metodo restituisce l'assembly del contenitore.</span><span class="sxs-lookup"><span data-stu-id="52220-110">If this assembly has been merged with others inside a single container assembly, this method returns the container assembly.</span></span> <span data-ttu-id="52220-111">Per altre informazioni e terminologia, vedere la [ICorDebugProcess6::EnableVirtualModuleSplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="52220-111">For more information and terminology, see the [ICorDebugProcess6::EnableVirtualModuleSplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52220-112">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="52220-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52220-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="52220-113">Requirements</span></span>  
 <span data-ttu-id="52220-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52220-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52220-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52220-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52220-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52220-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52220-117">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52220-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52220-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52220-118">See also</span></span>

- [<span data-ttu-id="52220-119">Interfaccia ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="52220-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [<span data-ttu-id="52220-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="52220-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
