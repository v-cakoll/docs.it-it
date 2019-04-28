---
title: Metodo ICorDebugDataTarget2::EnumerateThreadIDs
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 70b3b57b51faed51aa7d5a70a3b785e0f719321b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916565"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="ad11f-102">Metodo ICorDebugDataTarget2::EnumerateThreadIDs</span><span class="sxs-lookup"><span data-stu-id="ad11f-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="ad11f-103">Restituisce un elenco di ID thread attivi.</span><span class="sxs-lookup"><span data-stu-id="ad11f-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad11f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ad11f-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,   
    [out] ULONG32 *pcThreadIds,   
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad11f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ad11f-105">Parameters</span></span>  
 <span data-ttu-id="ad11f-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="ad11f-106">cThreadIDs</span></span>  
 <span data-ttu-id="ad11f-107">[in] Il numero massimo di thread con ID che possono essere restituiti.</span><span class="sxs-lookup"><span data-stu-id="ad11f-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="ad11f-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="ad11f-108">pcThreadIds</span></span>  
 <span data-ttu-id="ad11f-109">[out] Un puntatore a `ULONG32` che indica il numero effettivo di ID thread scritti nella matrice `pThreadIds`.</span><span class="sxs-lookup"><span data-stu-id="ad11f-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="ad11f-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="ad11f-110">pThreadIDs</span></span>  
 <span data-ttu-id="ad11f-111">Una matrice di identificatori di thread.</span><span class="sxs-lookup"><span data-stu-id="ad11f-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad11f-112">Note</span><span class="sxs-lookup"><span data-stu-id="ad11f-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad11f-113">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ad11f-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad11f-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ad11f-114">Requirements</span></span>  
 <span data-ttu-id="ad11f-115">**Piattaforme:** Visualizzare [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md). **Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad11f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad11f-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad11f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad11f-117">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad11f-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad11f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad11f-118">See also</span></span>

- [<span data-ttu-id="ad11f-119">Interfaccia ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="ad11f-119">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="ad11f-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ad11f-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
