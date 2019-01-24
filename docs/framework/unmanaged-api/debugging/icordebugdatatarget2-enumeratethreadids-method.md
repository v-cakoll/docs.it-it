---
title: Metodo ICorDebugDataTarget2::EnumerateThreadIDs
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 594fcb74988cadaa4801fc6f0bb2d05b27a7f441
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563392"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="0fb90-102">Metodo ICorDebugDataTarget2::EnumerateThreadIDs</span><span class="sxs-lookup"><span data-stu-id="0fb90-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="0fb90-103">Restituisce un elenco di ID thread attivi.</span><span class="sxs-lookup"><span data-stu-id="0fb90-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fb90-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0fb90-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,   
    [out] ULONG32 *pcThreadIds,   
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0fb90-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0fb90-105">Parameters</span></span>  
 <span data-ttu-id="0fb90-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="0fb90-106">cThreadIDs</span></span>  
 <span data-ttu-id="0fb90-107">[in] Il numero massimo di thread con ID che possono essere restituiti.</span><span class="sxs-lookup"><span data-stu-id="0fb90-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="0fb90-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="0fb90-108">pcThreadIds</span></span>  
 <span data-ttu-id="0fb90-109">[out] Un puntatore a `ULONG32` che indica il numero effettivo di ID thread scritti nella matrice `pThreadIds`.</span><span class="sxs-lookup"><span data-stu-id="0fb90-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="0fb90-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="0fb90-110">pThreadIDs</span></span>  
 <span data-ttu-id="0fb90-111">Una matrice di identificatori di thread.</span><span class="sxs-lookup"><span data-stu-id="0fb90-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0fb90-112">Note</span><span class="sxs-lookup"><span data-stu-id="0fb90-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0fb90-113">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0fb90-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fb90-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0fb90-114">Requirements</span></span>  
 <span data-ttu-id="0fb90-115">**Piattaforme:** Visualizzare [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md). **Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0fb90-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0fb90-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fb90-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fb90-117">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fb90-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fb90-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0fb90-118">See also</span></span>
- [<span data-ttu-id="0fb90-119">Interfaccia ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="0fb90-119">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="0fb90-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0fb90-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
