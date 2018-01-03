---
title: Metodo ICorDebugDebugEvent::GetThread
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: faf1ace6c65f38e9a1d5b958b633c95dbcd3dcf8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="4d4c5-102">Metodo ICorDebugDebugEvent::GetThread</span><span class="sxs-lookup"><span data-stu-id="4d4c5-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="4d4c5-103">Ottiene il thread in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="4d4c5-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d4c5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d4c5-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4d4c5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4d4c5-105">Parameters</span></span>  
 <span data-ttu-id="4d4c5-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="4d4c5-106">ppThread</span></span>  
 <span data-ttu-id="4d4c5-107">[out] Un puntatore all'indirizzo di un oggetto ICorDebugThread che rappresenta il thread su cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="4d4c5-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d4c5-108">Note</span><span class="sxs-lookup"><span data-stu-id="4d4c5-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d4c5-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4d4c5-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d4c5-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4d4c5-110">Requirements</span></span>  
 <span data-ttu-id="4d4c5-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d4c5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d4c5-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="4d4c5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d4c5-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d4c5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d4c5-114">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d4c5-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d4c5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d4c5-115">See Also</span></span>  
 [<span data-ttu-id="4d4c5-116">Interfaccia ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="4d4c5-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 [<span data-ttu-id="4d4c5-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4d4c5-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
