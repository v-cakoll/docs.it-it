---
title: Metodo ICorDebugAppDomain4::GetObjectForCCW
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
ms.openlocfilehash: 8b046eb5926bb9aa4738e8fff8e61b0b7c23a3aa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088834"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="97f31-102">Metodo ICorDebugAppDomain4::GetObjectForCCW</span><span class="sxs-lookup"><span data-stu-id="97f31-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="97f31-103">Ottiene un oggetto gestito da un puntatore a COM Callable Wrapper (CCW)</span><span class="sxs-lookup"><span data-stu-id="97f31-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97f31-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97f31-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97f31-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="97f31-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="97f31-106">[in] Puntatore a COM Callable Wrapper (CCW)</span><span class="sxs-lookup"><span data-stu-id="97f31-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="97f31-107">out Puntatore all'indirizzo di un oggetto "ICorDebugValue" che rappresenta l'oggetto gestito che corrisponde al puntatore CCW specificato.</span><span class="sxs-lookup"><span data-stu-id="97f31-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97f31-108">Note</span><span class="sxs-lookup"><span data-stu-id="97f31-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97f31-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="97f31-109">Requirements</span></span>  
 <span data-ttu-id="97f31-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97f31-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97f31-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97f31-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97f31-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97f31-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97f31-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97f31-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97f31-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97f31-114">See also</span></span>

- [<span data-ttu-id="97f31-115">Interfaccia ICorDebugAppDomain4</span><span class="sxs-lookup"><span data-stu-id="97f31-115">ICorDebugAppDomain4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)
- [<span data-ttu-id="97f31-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="97f31-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
