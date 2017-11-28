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
ms.openlocfilehash: 13b950545c2c8c8b54d24b932351d80280e1dac0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="e4d44-102">Metodo ICorDebugDebugEvent::GetThread</span><span class="sxs-lookup"><span data-stu-id="e4d44-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="e4d44-103">Ottiene il thread in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="e4d44-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4d44-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e4d44-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e4d44-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e4d44-105">Parameters</span></span>  
 <span data-ttu-id="e4d44-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="e4d44-106">ppThread</span></span>  
 <span data-ttu-id="e4d44-107">[out] Un puntatore all'indirizzo di un oggetto ICorDebugThread che rappresenta il thread su cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="e4d44-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4d44-108">Note</span><span class="sxs-lookup"><span data-stu-id="e4d44-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4d44-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e4d44-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4d44-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e4d44-110">Requirements</span></span>  
 <span data-ttu-id="e4d44-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4d44-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4d44-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="e4d44-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4d44-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4d44-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4d44-114">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4d44-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4d44-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4d44-115">See Also</span></span>  
 [<span data-ttu-id="e4d44-116">Interfaccia ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="e4d44-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 [<span data-ttu-id="e4d44-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e4d44-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
