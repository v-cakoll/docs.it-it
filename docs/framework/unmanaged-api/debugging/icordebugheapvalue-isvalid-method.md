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
ms.openlocfilehash: e774905939640d2748344ad3f6e12a96f9868d9f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213803"
---
# <a name="icordebugheapvalueisvalid-method"></a><span data-ttu-id="4b3ac-102">Metodo ICorDebugHeapValue::IsValid</span><span class="sxs-lookup"><span data-stu-id="4b3ac-102">ICorDebugHeapValue::IsValid Method</span></span>
<span data-ttu-id="4b3ac-103">Ottiene un valore che indica se l'oggetto rappresentato da questo ICorDebugHeapValue è valido.</span><span class="sxs-lookup"><span data-stu-id="4b3ac-103">Gets a value that indicates whether the object represented by this ICorDebugHeapValue is valid.</span></span>  
  
 <span data-ttu-id="4b3ac-104">Questo metodo è stato deprecato nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="4b3ac-104">This method has been deprecated in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b3ac-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b3ac-105">Syntax</span></span>  
  
```cpp  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b3ac-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="4b3ac-106">Parameters</span></span>  
 `pbValid`  
 <span data-ttu-id="4b3ac-107">out Puntatore a un valore booleano che indica se questo valore nell'heap è valido.</span><span class="sxs-lookup"><span data-stu-id="4b3ac-107">[out] A pointer to a Boolean value that indicates whether this value on the heap is valid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b3ac-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4b3ac-108">Remarks</span></span>  
 <span data-ttu-id="4b3ac-109">Il valore non è valido se è stato recuperato dal Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="4b3ac-109">The value is invalid if it has been reclaimed by the garbage collector.</span></span>  
  
 <span data-ttu-id="4b3ac-110">Questo metodo è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="4b3ac-110">This method has been deprecated.</span></span> <span data-ttu-id="4b3ac-111">Nel .NET Framework 2,0, tutti i valori sono validi fino a quando non viene chiamato [ICorDebugController:: continue](icordebugcontroller-continue-method.md) , quindi i valori vengono invalidati.</span><span class="sxs-lookup"><span data-stu-id="4b3ac-111">In the .NET Framework 2.0, all values are valid until [ICorDebugController::Continue](icordebugcontroller-continue-method.md) is called, at which time the values are invalidated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b3ac-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4b3ac-112">Requirements</span></span>  
 <span data-ttu-id="4b3ac-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b3ac-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b3ac-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b3ac-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b3ac-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b3ac-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b3ac-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b3ac-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
