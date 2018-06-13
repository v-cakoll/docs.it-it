---
title: Metodo ICorDebugAppDomain4::GetObjectForCCW
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1089668aa19747f5f694360ebb87098e2df9ad4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405551"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="d6c89-102">Metodo ICorDebugAppDomain4::GetObjectForCCW</span><span class="sxs-lookup"><span data-stu-id="d6c89-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="d6c89-103">Ottiene un oggetto gestito da un puntatore a COM Callable Wrapper (CCW)</span><span class="sxs-lookup"><span data-stu-id="d6c89-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6c89-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6c89-104">Syntax</span></span>  
  
```  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d6c89-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d6c89-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="d6c89-106">[in] Puntatore a COM Callable Wrapper (CCW)</span><span class="sxs-lookup"><span data-stu-id="d6c89-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="d6c89-107">[out] Un puntatore all'indirizzo di un oggetto "ICorDebugValue" che rappresenta l'oggetto gestito che corrisponde al puntatore CCW specificato.</span><span class="sxs-lookup"><span data-stu-id="d6c89-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6c89-108">Note</span><span class="sxs-lookup"><span data-stu-id="d6c89-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6c89-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d6c89-109">Requirements</span></span>  
 <span data-ttu-id="d6c89-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6c89-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6c89-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="d6c89-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6c89-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="d6c89-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6c89-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6c89-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6c89-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6c89-114">See Also</span></span>  
 [<span data-ttu-id="d6c89-115">Interfaccia ICorDebugAppDomain4</span><span class="sxs-lookup"><span data-stu-id="d6c89-115">ICorDebugAppDomain4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)  
 [<span data-ttu-id="d6c89-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d6c89-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
