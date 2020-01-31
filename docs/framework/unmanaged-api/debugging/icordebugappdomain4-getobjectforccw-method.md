---
title: Metodo ICorDebugAppDomain4::GetObjectForCCW
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
ms.openlocfilehash: 50f46394c809321f0bd256e4c8d75b76fc7c2c70
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784856"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="54837-102">Metodo ICorDebugAppDomain4::GetObjectForCCW</span><span class="sxs-lookup"><span data-stu-id="54837-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="54837-103">Ottiene un oggetto gestito da un puntatore a COM Callable Wrapper (CCW)</span><span class="sxs-lookup"><span data-stu-id="54837-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54837-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="54837-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54837-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="54837-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="54837-106">[in] Puntatore a COM Callable Wrapper (CCW)</span><span class="sxs-lookup"><span data-stu-id="54837-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="54837-107">out Puntatore all'indirizzo di un oggetto "ICorDebugValue" che rappresenta l'oggetto gestito che corrisponde al puntatore CCW specificato.</span><span class="sxs-lookup"><span data-stu-id="54837-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54837-108">Note</span><span class="sxs-lookup"><span data-stu-id="54837-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54837-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="54837-109">Requirements</span></span>  
 <span data-ttu-id="54837-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54837-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54837-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54837-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54837-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54837-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54837-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54837-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54837-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54837-114">See also</span></span>

- [<span data-ttu-id="54837-115">Interfaccia ICorDebugAppDomain4</span><span class="sxs-lookup"><span data-stu-id="54837-115">ICorDebugAppDomain4 Interface</span></span>](icordebugappdomain4-interface.md)
- [<span data-ttu-id="54837-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="54837-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
