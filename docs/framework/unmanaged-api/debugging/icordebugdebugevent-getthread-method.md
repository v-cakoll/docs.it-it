---
title: Metodo ICorDebugDebugEvent::GetThread
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c5b4a15f637526cd2faadd2d9d3da143c40140f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414905"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="3d167-102">Metodo ICorDebugDebugEvent::GetThread</span><span class="sxs-lookup"><span data-stu-id="3d167-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="3d167-103">Ottiene il thread in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="3d167-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d167-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d167-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d167-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3d167-105">Parameters</span></span>  
 <span data-ttu-id="3d167-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="3d167-106">ppThread</span></span>  
 <span data-ttu-id="3d167-107">[out] Un puntatore all'indirizzo di un oggetto ICorDebugThread che rappresenta il thread su cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="3d167-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d167-108">Note</span><span class="sxs-lookup"><span data-stu-id="3d167-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d167-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3d167-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d167-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3d167-110">Requirements</span></span>  
 <span data-ttu-id="3d167-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d167-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d167-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="3d167-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d167-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="3d167-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d167-114">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d167-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d167-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d167-115">See Also</span></span>  
 [<span data-ttu-id="3d167-116">Interfaccia ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="3d167-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 [<span data-ttu-id="3d167-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3d167-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
