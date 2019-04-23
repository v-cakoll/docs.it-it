---
title: Metodo ICorDebugValue3::GetSize64
ms.date: 03/30/2017
api_name:
- ICorDebugValue3::GetSize64
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3::GetSize64
helpviewer_keywords:
- GetSize64 method, ICorDebugValue3 interface [.NET Framework debugging]
- ICorDebugValue3::GetSize64 method [.NET Framework debugging]
ms.assetid: fee56a29-3154-4192-958d-71da2ced3740
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c0b45e08f7b88d9374023f95c6e3e22139c8949
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59144768"
---
# <a name="icordebugvalue3getsize64-method"></a><span data-ttu-id="ec36f-102">Metodo ICorDebugValue3::GetSize64</span><span class="sxs-lookup"><span data-stu-id="ec36f-102">ICorDebugValue3::GetSize64 Method</span></span>
<span data-ttu-id="ec36f-103">Ottiene la dimensione, espressa in byte, di questo [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="ec36f-103">Gets the size, in bytes, of this [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec36f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ec36f-104">Syntax</span></span>  
  
```  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec36f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ec36f-105">Parameters</span></span>  
 <span data-ttu-id="ec36f-106">pSize</span><span class="sxs-lookup"><span data-stu-id="ec36f-106">pSize</span></span>  
 <span data-ttu-id="ec36f-107">[out] Un puntatore alla dimensione, espressa in byte, di questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="ec36f-107">[out] A pointer to the size, in bytes, of this object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec36f-108">Note</span><span class="sxs-lookup"><span data-stu-id="ec36f-108">Remarks</span></span>  
 <span data-ttu-id="ec36f-109">Se questo tipo di valore è un tipo riferimento, questo metodo restituisce la dimensione del puntatore anziché le dimensioni dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="ec36f-109">If this value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="ec36f-110">Il `ICorDebugValue3::GetSize` metodo si differenzia dal [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) metodo nel tipo del relativo parametro di output.</span><span class="sxs-lookup"><span data-stu-id="ec36f-110">The `ICorDebugValue3::GetSize` method differs from the [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) method in the type of its output parameter.</span></span> <span data-ttu-id="ec36f-111">Nelle [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), il parametro di output è un `ULONG32`; nella `ICorDebugValue3::GetSize`, è un `ULONG64`.</span><span class="sxs-lookup"><span data-stu-id="ec36f-111">In [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), the output parameter is a `ULONG32`; in `ICorDebugValue3::GetSize`, it is a `ULONG64`.</span></span> <span data-ttu-id="ec36f-112">In questo modo, il [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) interfaccia per segnalare le dimensioni delle matrici che superano 2 GB.</span><span class="sxs-lookup"><span data-stu-id="ec36f-112">This enables the [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) interface to report the size of arrays that exceed 2GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec36f-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ec36f-113">Requirements</span></span>  
 <span data-ttu-id="ec36f-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec36f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec36f-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec36f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec36f-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec36f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec36f-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec36f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec36f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec36f-118">See also</span></span>

- [<span data-ttu-id="ec36f-119">Interfaccia ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="ec36f-119">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [<span data-ttu-id="ec36f-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ec36f-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
