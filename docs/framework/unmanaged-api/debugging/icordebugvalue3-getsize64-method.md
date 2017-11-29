---
title: Metodo ICorDebugValue3::GetSize64
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue3::GetSize64
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue3::GetSize64
helpviewer_keywords:
- GetSize64 method, ICorDebugValue3 interface [.NET Framework debugging]
- ICorDebugValue3::GetSize64 method [.NET Framework debugging]
ms.assetid: fee56a29-3154-4192-958d-71da2ced3740
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b129ebe666972052775c2c3e44e38bb6a25a176e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvalue3getsize64-method"></a><span data-ttu-id="426d7-102">Metodo ICorDebugValue3::GetSize64</span><span class="sxs-lookup"><span data-stu-id="426d7-102">ICorDebugValue3::GetSize64 Method</span></span>
<span data-ttu-id="426d7-103">Ottiene le dimensioni, in byte, di questo [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="426d7-103">Gets the size, in bytes, of this [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="426d7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="426d7-104">Syntax</span></span>  
  
```  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="426d7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="426d7-105">Parameters</span></span>  
 <span data-ttu-id="426d7-106">pSize</span><span class="sxs-lookup"><span data-stu-id="426d7-106">pSize</span></span>  
 <span data-ttu-id="426d7-107">[out] Puntatore alla dimensione, in byte, di questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="426d7-107">[out] A pointer to the size, in bytes, of this object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="426d7-108">Note</span><span class="sxs-lookup"><span data-stu-id="426d7-108">Remarks</span></span>  
 <span data-ttu-id="426d7-109">Se questo tipo di valore è un tipo riferimento, questo metodo restituisce le dimensioni dell'indicatore di misura anziché la dimensione dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="426d7-109">If this value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="426d7-110">Il `ICorDebugValue3::GetSize` metodo differisce dal [ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) metodo nel tipo del parametro di output.</span><span class="sxs-lookup"><span data-stu-id="426d7-110">The `ICorDebugValue3::GetSize` method differs from the [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) method in the type of its output parameter.</span></span> <span data-ttu-id="426d7-111">In [ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), il parametro di output è un `ULONG32`; in `ICorDebugValue3::GetSize`, si tratta di un `ULONG64`.</span><span class="sxs-lookup"><span data-stu-id="426d7-111">In [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), the output parameter is a `ULONG32`; in `ICorDebugValue3::GetSize`, it is a `ULONG64`.</span></span> <span data-ttu-id="426d7-112">In questo modo il [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) interfaccia per segnalare le dimensioni delle matrici che superano 2 GB.</span><span class="sxs-lookup"><span data-stu-id="426d7-112">This enables the [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) interface to report the size of arrays that exceed 2GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="426d7-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="426d7-113">Requirements</span></span>  
 <span data-ttu-id="426d7-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="426d7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="426d7-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="426d7-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="426d7-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="426d7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="426d7-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="426d7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="426d7-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="426d7-118">See Also</span></span>  
 [<span data-ttu-id="426d7-119">ICorDebugValue3 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="426d7-119">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 [<span data-ttu-id="426d7-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="426d7-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
