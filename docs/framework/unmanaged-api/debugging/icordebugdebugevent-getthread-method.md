---
title: Metodo ICorDebugDebugEvent::GetThread
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f85dccd5b59610c52adcf685828984c9344fd49
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911278"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="a5556-102">Metodo ICorDebugDebugEvent::GetThread</span><span class="sxs-lookup"><span data-stu-id="a5556-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="a5556-103">Ottiene il thread in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="a5556-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5556-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a5556-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5556-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a5556-105">Parameters</span></span>  
 <span data-ttu-id="a5556-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="a5556-106">ppThread</span></span>  
 <span data-ttu-id="a5556-107">out Puntatore all'indirizzo di un oggetto ICorDebugThread che rappresenta il thread in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="a5556-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5556-108">Note</span><span class="sxs-lookup"><span data-stu-id="a5556-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5556-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a5556-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5556-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a5556-110">Requirements</span></span>  
 <span data-ttu-id="a5556-111">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5556-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5556-112">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="a5556-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5556-113">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5556-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5556-114">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5556-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5556-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5556-115">See also</span></span>

- [<span data-ttu-id="a5556-116">Interfaccia ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="a5556-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="a5556-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a5556-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
