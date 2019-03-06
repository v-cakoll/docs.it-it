---
title: Metodo ICorDebugDebugEvent::GetThread
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 403caa136f85904937bd5077a618e5aed788c86a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472304"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="6a674-102">Metodo ICorDebugDebugEvent::GetThread</span><span class="sxs-lookup"><span data-stu-id="6a674-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="6a674-103">Ottiene il thread in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="6a674-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a674-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6a674-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a674-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6a674-105">Parameters</span></span>  
 <span data-ttu-id="6a674-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="6a674-106">ppThread</span></span>  
 <span data-ttu-id="6a674-107">[out] Un puntatore all'indirizzo di un oggetto ICorDebugThread che rappresenta il thread in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="6a674-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a674-108">Note</span><span class="sxs-lookup"><span data-stu-id="6a674-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a674-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6a674-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a674-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6a674-110">Requirements</span></span>  
 <span data-ttu-id="6a674-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a674-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a674-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a674-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a674-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a674-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a674-114">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a674-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a674-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a674-115">See also</span></span>
- [<span data-ttu-id="6a674-116">Interfaccia ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="6a674-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="6a674-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6a674-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
