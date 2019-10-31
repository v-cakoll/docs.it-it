---
title: Metodo ICorDebugHeapValue::IsValid
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue.IsValid
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue::IsValid
helpviewer_keywords:
- IsValid method [.NET Framework debugging]
- ICorDebugHeapValue::IsValid method [.NET Framework debugging]
ms.assetid: 68e20e62-203d-46d8-bb91-8d3c61cfacc3
topic_type:
- apiref
ms.openlocfilehash: 7edf0065fa7eb39dada167a682f2b634a438f1f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138404"
---
# <a name="icordebugheapvalueisvalid-method"></a><span data-ttu-id="54c8d-102">Metodo ICorDebugHeapValue::IsValid</span><span class="sxs-lookup"><span data-stu-id="54c8d-102">ICorDebugHeapValue::IsValid Method</span></span>
<span data-ttu-id="54c8d-103">Ottiene un valore che indica se l'oggetto rappresentato da questo ICorDebugHeapValue è valido.</span><span class="sxs-lookup"><span data-stu-id="54c8d-103">Gets a value that indicates whether the object represented by this ICorDebugHeapValue is valid.</span></span>  
  
 <span data-ttu-id="54c8d-104">Questo metodo è stato deprecato nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="54c8d-104">This method has been deprecated in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54c8d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="54c8d-105">Syntax</span></span>  
  
```cpp  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54c8d-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="54c8d-106">Parameters</span></span>  
 `pbValid`  
 <span data-ttu-id="54c8d-107">out Puntatore a un valore booleano che indica se questo valore nell'heap è valido.</span><span class="sxs-lookup"><span data-stu-id="54c8d-107">[out] A pointer to a Boolean value that indicates whether this value on the heap is valid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54c8d-108">Note</span><span class="sxs-lookup"><span data-stu-id="54c8d-108">Remarks</span></span>  
 <span data-ttu-id="54c8d-109">Il valore non è valido se è stato recuperato dal Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="54c8d-109">The value is invalid if it has been reclaimed by the garbage collector.</span></span>  
  
 <span data-ttu-id="54c8d-110">Questo metodo è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="54c8d-110">This method has been deprecated.</span></span> <span data-ttu-id="54c8d-111">Nel .NET Framework 2,0, tutti i valori sono validi fino a quando non viene chiamato [ICorDebugController:: continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) , quindi i valori vengono invalidati.</span><span class="sxs-lookup"><span data-stu-id="54c8d-111">In the .NET Framework 2.0, all values are valid until [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called, at which time the values are invalidated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54c8d-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="54c8d-112">Requirements</span></span>  
 <span data-ttu-id="54c8d-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54c8d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54c8d-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54c8d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54c8d-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54c8d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54c8d-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54c8d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
