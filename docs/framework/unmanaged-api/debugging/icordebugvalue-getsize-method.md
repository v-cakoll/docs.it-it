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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94d8fbf4d93bbfbaaeb7c1268004aada22b9b7df
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768920"
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="cc5e9-102">Metodo ICorDebugValue::GetSize</span><span class="sxs-lookup"><span data-stu-id="cc5e9-102">ICorDebugValue::GetSize Method</span></span>
<span data-ttu-id="cc5e9-103">Ottiene la dimensione, espressa in byte, dell'oggetto "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="cc5e9-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc5e9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cc5e9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc5e9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cc5e9-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="cc5e9-106">[out] Le dimensioni, in byte, dell'oggetto valore.</span><span class="sxs-lookup"><span data-stu-id="cc5e9-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc5e9-107">Note</span><span class="sxs-lookup"><span data-stu-id="cc5e9-107">Remarks</span></span>  
 <span data-ttu-id="cc5e9-108">Se il tipo del valore è un tipo riferimento, questo metodo restituisce la dimensione del puntatore anziché le dimensioni dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="cc5e9-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="cc5e9-109">Il `ICorDebugValue::GetSize` restituzione del metodo `COR_E_OVERFLOW` per gli oggetti di dimensioni superiori a 4 GB su piattaforme a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="cc5e9-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="cc5e9-110">Usare la [ICorDebugValue3::GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) metodo invece per gli oggetti che sono maggiori di 4 GB.</span><span class="sxs-lookup"><span data-stu-id="cc5e9-110">Use the [ICorDebugValue3::GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc5e9-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cc5e9-111">Requirements</span></span>  
 <span data-ttu-id="cc5e9-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc5e9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc5e9-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc5e9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc5e9-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc5e9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc5e9-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc5e9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc5e9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc5e9-116">See also</span></span>

- [<span data-ttu-id="cc5e9-117">Metodo GetSize64</span><span class="sxs-lookup"><span data-stu-id="cc5e9-117">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)
