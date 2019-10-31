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
ms.openlocfilehash: 72a1b6fdc40f3169500d8cf3b3028315106ecc69
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140236"
---
# <a name="icordebugvalue3getsize64-method"></a><span data-ttu-id="55c6b-102">Metodo ICorDebugValue3::GetSize64</span><span class="sxs-lookup"><span data-stu-id="55c6b-102">ICorDebugValue3::GetSize64 Method</span></span>
<span data-ttu-id="55c6b-103">Ottiene la dimensione in byte di questo oggetto [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="55c6b-103">Gets the size, in bytes, of this [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55c6b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="55c6b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55c6b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="55c6b-105">Parameters</span></span>  
 <span data-ttu-id="55c6b-106">pSize</span><span class="sxs-lookup"><span data-stu-id="55c6b-106">pSize</span></span>  
 <span data-ttu-id="55c6b-107">out Puntatore alla dimensione, in byte, dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="55c6b-107">[out] A pointer to the size, in bytes, of this object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55c6b-108">Note</span><span class="sxs-lookup"><span data-stu-id="55c6b-108">Remarks</span></span>  
 <span data-ttu-id="55c6b-109">Se il tipo di questo valore è un tipo di riferimento, questo metodo restituisce le dimensioni del puntatore anziché le dimensioni dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="55c6b-109">If this value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="55c6b-110">Il metodo `ICorDebugValue3::GetSize` differisce dal metodo [ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) nel tipo del parametro di output.</span><span class="sxs-lookup"><span data-stu-id="55c6b-110">The `ICorDebugValue3::GetSize` method differs from the [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) method in the type of its output parameter.</span></span> <span data-ttu-id="55c6b-111">In [ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), il parametro di output è un `ULONG32`; in `ICorDebugValue3::GetSize`, si tratta di un `ULONG64`.</span><span class="sxs-lookup"><span data-stu-id="55c6b-111">In [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), the output parameter is a `ULONG32`; in `ICorDebugValue3::GetSize`, it is a `ULONG64`.</span></span> <span data-ttu-id="55c6b-112">Ciò consente all'interfaccia [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) di segnalare le dimensioni delle matrici che superano 2 GB.</span><span class="sxs-lookup"><span data-stu-id="55c6b-112">This enables the [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) interface to report the size of arrays that exceed 2GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55c6b-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="55c6b-113">Requirements</span></span>  
 <span data-ttu-id="55c6b-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55c6b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55c6b-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55c6b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55c6b-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55c6b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55c6b-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55c6b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c6b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55c6b-118">See also</span></span>

- [<span data-ttu-id="55c6b-119">Interfaccia ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="55c6b-119">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [<span data-ttu-id="55c6b-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="55c6b-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
