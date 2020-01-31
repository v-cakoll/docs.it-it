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
ms.openlocfilehash: 7ae06d825565faff70b0c8be2ccbee5228737e41
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791095"
---
# <a name="icordebugvalue3getsize64-method"></a><span data-ttu-id="7c435-102">Metodo ICorDebugValue3::GetSize64</span><span class="sxs-lookup"><span data-stu-id="7c435-102">ICorDebugValue3::GetSize64 Method</span></span>
<span data-ttu-id="7c435-103">Ottiene la dimensione in byte di questo oggetto [ICorDebugValue3](icordebugvalue3-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="7c435-103">Gets the size, in bytes, of this [ICorDebugValue3](icordebugvalue3-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c435-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7c435-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c435-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7c435-105">Parameters</span></span>  
 <span data-ttu-id="7c435-106">pSize</span><span class="sxs-lookup"><span data-stu-id="7c435-106">pSize</span></span>  
 <span data-ttu-id="7c435-107">out Puntatore alla dimensione, in byte, dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="7c435-107">[out] A pointer to the size, in bytes, of this object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c435-108">Note</span><span class="sxs-lookup"><span data-stu-id="7c435-108">Remarks</span></span>  
 <span data-ttu-id="7c435-109">Se il tipo di questo valore è un tipo di riferimento, questo metodo restituisce le dimensioni del puntatore anziché le dimensioni dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="7c435-109">If this value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="7c435-110">Il metodo `ICorDebugValue3::GetSize` differisce dal metodo [ICorDebugValue:: GetSize](icordebugvalue-getsize-method.md) nel tipo del parametro di output.</span><span class="sxs-lookup"><span data-stu-id="7c435-110">The `ICorDebugValue3::GetSize` method differs from the [ICorDebugValue::GetSize](icordebugvalue-getsize-method.md) method in the type of its output parameter.</span></span> <span data-ttu-id="7c435-111">In [ICorDebugValue:: GetSize](icordebugvalue-getsize-method.md), il parametro di output è un `ULONG32`; in `ICorDebugValue3::GetSize`, si tratta di un `ULONG64`.</span><span class="sxs-lookup"><span data-stu-id="7c435-111">In [ICorDebugValue::GetSize](icordebugvalue-getsize-method.md), the output parameter is a `ULONG32`; in `ICorDebugValue3::GetSize`, it is a `ULONG64`.</span></span> <span data-ttu-id="7c435-112">Ciò consente all'interfaccia [ICorDebugValue3](icordebugvalue3-interface.md) di segnalare le dimensioni delle matrici che superano 2 GB.</span><span class="sxs-lookup"><span data-stu-id="7c435-112">This enables the [ICorDebugValue3](icordebugvalue3-interface.md) interface to report the size of arrays that exceed 2GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c435-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="7c435-113">Requirements</span></span>  
 <span data-ttu-id="7c435-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c435-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c435-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c435-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c435-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c435-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c435-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c435-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c435-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c435-118">See also</span></span>

- [<span data-ttu-id="7c435-119">Interfaccia ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="7c435-119">ICorDebugValue3 Interface</span></span>](icordebugvalue3-interface.md)
- [<span data-ttu-id="7c435-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="7c435-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
