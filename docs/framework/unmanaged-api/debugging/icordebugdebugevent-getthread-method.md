---
title: Metodo ICorDebugDebugEvent::GetThread
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
ms.openlocfilehash: 0900ac2ae5bcf2141e720dad6efdf68d4fafaccc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793526"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="75e93-102">Metodo ICorDebugDebugEvent::GetThread</span><span class="sxs-lookup"><span data-stu-id="75e93-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="75e93-103">Ottiene il thread in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="75e93-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75e93-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="75e93-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75e93-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="75e93-105">Parameters</span></span>  
 <span data-ttu-id="75e93-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="75e93-106">ppThread</span></span>  
 <span data-ttu-id="75e93-107">[out] Un puntatore all'indirizzo di un oggetto ICorDebugThread che rappresenta il thread in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="75e93-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75e93-108">Note</span><span class="sxs-lookup"><span data-stu-id="75e93-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="75e93-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="75e93-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75e93-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="75e93-110">Requirements</span></span>  
 <span data-ttu-id="75e93-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75e93-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75e93-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75e93-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75e93-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75e93-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75e93-114">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75e93-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75e93-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75e93-115">See also</span></span>

- [<span data-ttu-id="75e93-116">Interfaccia ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="75e93-116">ICorDebugDebugEvent Interface</span></span>](icordebugdebugevent-interface.md)
- [<span data-ttu-id="75e93-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="75e93-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
