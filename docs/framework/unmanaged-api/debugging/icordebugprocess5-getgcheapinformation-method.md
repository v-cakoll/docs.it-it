---
title: Metodo ICorDebugProcess5::GetGCHeapInformation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.GetGCHeapInformation
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::GetGCHeapInformation
helpviewer_keywords:
- ICorDebugProcess5::GetGCHeapInformation method [.NET Framework debugging]
- GetGCHeapInformation method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: b9538ceb-230a-4079-9cb2-903dbf5c1848
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: da423914d8af20c0f942d53ed6ac9f34ace01ca9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="191f9-102">Metodo ICorDebugProcess5::GetGCHeapInformation</span><span class="sxs-lookup"><span data-stu-id="191f9-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>
<span data-ttu-id="191f9-103">Fornisce informazioni generali sull'heap di garbage collection, ad esempio se è attualmente enumerabile.</span><span class="sxs-lookup"><span data-stu-id="191f9-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="191f9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="191f9-104">Syntax</span></span>  
  
```  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="191f9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="191f9-105">Parameters</span></span>  
 `pHeapInfo`  
 <span data-ttu-id="191f9-106">[out] Un puntatore a un [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) valore che fornisce informazioni generali sull'heap di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="191f9-106">[out] A pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="191f9-107">Note</span><span class="sxs-lookup"><span data-stu-id="191f9-107">Remarks</span></span>  
 <span data-ttu-id="191f9-108">Il `ICorDebugProcess5::GetGCHeapInformation` metodo deve essere chiamato prima l'enumerazione dell'heap o aree di heap singoli per garantire che le strutture di garbage collection del processo attualmente vengono.</span><span class="sxs-lookup"><span data-stu-id="191f9-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="191f9-109">Heap di garbage collection non può essere esaminata mentre è in corso una raccolta.</span><span class="sxs-lookup"><span data-stu-id="191f9-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="191f9-110">In caso contrario, l'enumerazione potrebbe acquisire strutture di garbage collection che non sono validi.</span><span class="sxs-lookup"><span data-stu-id="191f9-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="191f9-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="191f9-111">Requirements</span></span>  
 <span data-ttu-id="191f9-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="191f9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="191f9-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="191f9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="191f9-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="191f9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="191f9-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="191f9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="191f9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="191f9-116">See Also</span></span>  
 [<span data-ttu-id="191f9-117">ICorDebugProcess5 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="191f9-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="191f9-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="191f9-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
