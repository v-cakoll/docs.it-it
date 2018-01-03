---
title: Metodo ICorDebugDataTarget2::EnumerateThreadIDs
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9030f7f8453de98f535cf8212e55c7daee94e8e1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="21543-102">Metodo ICorDebugDataTarget2::EnumerateThreadIDs</span><span class="sxs-lookup"><span data-stu-id="21543-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="21543-103">Restituisce un elenco di ID thread attivi.</span><span class="sxs-lookup"><span data-stu-id="21543-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21543-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="21543-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,   
    [out] ULONG32 *pcThreadIds,   
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="21543-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="21543-105">Parameters</span></span>  
 <span data-ttu-id="21543-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="21543-106">cThreadIDs</span></span>  
 <span data-ttu-id="21543-107">[in] Il numero massimo di thread con ID che possono essere restituiti.</span><span class="sxs-lookup"><span data-stu-id="21543-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="21543-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="21543-108">pcThreadIds</span></span>  
 <span data-ttu-id="21543-109">[out] Un puntatore a `ULONG32` che indica il numero effettivo di ID thread scritti nella matrice `pThreadIds`.</span><span class="sxs-lookup"><span data-stu-id="21543-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="21543-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="21543-110">pThreadIDs</span></span>  
 <span data-ttu-id="21543-111">Una matrice di identificatori di thread.</span><span class="sxs-lookup"><span data-stu-id="21543-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21543-112">Note</span><span class="sxs-lookup"><span data-stu-id="21543-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="21543-113">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="21543-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21543-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="21543-114">Requirements</span></span>  
 <span data-ttu-id="21543-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md). **Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="21543-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21543-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21543-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21543-117">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21543-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21543-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21543-118">See Also</span></span>  
 [<span data-ttu-id="21543-119">Interfaccia ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="21543-119">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [<span data-ttu-id="21543-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="21543-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
