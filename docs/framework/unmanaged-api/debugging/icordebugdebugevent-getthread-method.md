---
title: Metodo ICorDebugDebugEvent::GetThread
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bde1083fe232563aa6129cec79fdfc6c16c77d03
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750012"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="6c072-102">Metodo ICorDebugDebugEvent::GetThread</span><span class="sxs-lookup"><span data-stu-id="6c072-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="6c072-103">Ottiene il thread in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="6c072-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c072-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6c072-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c072-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6c072-105">Parameters</span></span>  
 <span data-ttu-id="6c072-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="6c072-106">ppThread</span></span>  
 <span data-ttu-id="6c072-107">[out] Un puntatore all'indirizzo di un oggetto ICorDebugThread che rappresenta il thread in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="6c072-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c072-108">Note</span><span class="sxs-lookup"><span data-stu-id="6c072-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c072-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6c072-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c072-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6c072-110">Requirements</span></span>  
 <span data-ttu-id="6c072-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c072-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c072-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6c072-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c072-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c072-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c072-114">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c072-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c072-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c072-115">See also</span></span>

- [<span data-ttu-id="6c072-116">Interfaccia ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="6c072-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="6c072-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6c072-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
