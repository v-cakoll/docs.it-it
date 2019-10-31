---
title: Metodo ICorDebugValue::GetSize
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugValue interface [.NET Framework debugging]
- ICorDebugValue::GetSize method [.NET Framework debugging]
ms.assetid: 445a9ee3-e050-4f3a-931a-96b0efb00110
topic_type:
- apiref
ms.openlocfilehash: 3d6caa02333229bcd49f4c6ccf8b93265181a0b3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137087"
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="75f60-102">Metodo ICorDebugValue::GetSize</span><span class="sxs-lookup"><span data-stu-id="75f60-102">ICorDebugValue::GetSize Method</span></span>
<span data-ttu-id="75f60-103">Ottiene le dimensioni in byte di questo oggetto "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="75f60-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75f60-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="75f60-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75f60-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="75f60-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="75f60-106">out Dimensione, in byte, di questo oggetto valore.</span><span class="sxs-lookup"><span data-stu-id="75f60-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75f60-107">Note</span><span class="sxs-lookup"><span data-stu-id="75f60-107">Remarks</span></span>  
 <span data-ttu-id="75f60-108">Se il tipo del valore è un tipo di riferimento, questo metodo restituisce le dimensioni del puntatore anziché le dimensioni dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="75f60-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="75f60-109">Il metodo `ICorDebugValue::GetSize` restituisce `COR_E_OVERFLOW` per oggetti con dimensioni maggiori di 4 GB su piattaforme a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="75f60-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="75f60-110">Usare invece il metodo [ICorDebugValue3:: GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) per gli oggetti con dimensioni maggiori di 4 GB.</span><span class="sxs-lookup"><span data-stu-id="75f60-110">Use the [ICorDebugValue3::GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75f60-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="75f60-111">Requirements</span></span>  
 <span data-ttu-id="75f60-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75f60-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75f60-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75f60-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75f60-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75f60-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75f60-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75f60-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75f60-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75f60-116">See also</span></span>

- [<span data-ttu-id="75f60-117">Metodo GetSize64</span><span class="sxs-lookup"><span data-stu-id="75f60-117">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)
