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
ms.openlocfilehash: 3d26ddb6d89af60acf6dc1214b0423ba75e488ff
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791172"
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="b7b20-102">Metodo ICorDebugValue::GetSize</span><span class="sxs-lookup"><span data-stu-id="b7b20-102">ICorDebugValue::GetSize Method</span></span>
<span data-ttu-id="b7b20-103">Ottiene le dimensioni in byte di questo oggetto "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="b7b20-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7b20-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b7b20-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7b20-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b7b20-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="b7b20-106">out Dimensione, in byte, di questo oggetto valore.</span><span class="sxs-lookup"><span data-stu-id="b7b20-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7b20-107">Note</span><span class="sxs-lookup"><span data-stu-id="b7b20-107">Remarks</span></span>  
 <span data-ttu-id="b7b20-108">Se il tipo del valore è un tipo di riferimento, questo metodo restituisce le dimensioni del puntatore anziché le dimensioni dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="b7b20-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="b7b20-109">Il metodo `ICorDebugValue::GetSize` restituisce `COR_E_OVERFLOW` per oggetti con dimensioni maggiori di 4 GB su piattaforme a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="b7b20-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="b7b20-110">Usare invece il metodo [ICorDebugValue3:: GetSize64](icordebugvalue3-getsize64-method.md) per gli oggetti con dimensioni maggiori di 4 GB.</span><span class="sxs-lookup"><span data-stu-id="b7b20-110">Use the [ICorDebugValue3::GetSize64](icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7b20-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="b7b20-111">Requirements</span></span>  
 <span data-ttu-id="b7b20-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7b20-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7b20-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7b20-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7b20-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7b20-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7b20-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7b20-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7b20-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7b20-116">See also</span></span>

- [<span data-ttu-id="b7b20-117">Metodo GetSize64</span><span class="sxs-lookup"><span data-stu-id="b7b20-117">GetSize64 Method</span></span>](icordebugvalue3-getsize64-method.md)
