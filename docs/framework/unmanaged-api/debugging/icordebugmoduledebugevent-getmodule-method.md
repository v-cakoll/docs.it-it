---
title: Metodo ICorDebugModuleDebugEvent::GetModule
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b11ab8991a9f44cf2868474a8a0f6dcc1c3308c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="9ff12-102">Metodo ICorDebugModuleDebugEvent::GetModule</span><span class="sxs-lookup"><span data-stu-id="9ff12-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="9ff12-103">Ottiene il modulo unito appena caricato o scaricato.</span><span class="sxs-lookup"><span data-stu-id="9ff12-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ff12-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9ff12-104">Syntax</span></span>  
  
```  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ff12-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9ff12-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="9ff12-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugModule che rappresenta il modulo unito che è stato appena caricato o scaricato.</span><span class="sxs-lookup"><span data-stu-id="9ff12-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ff12-107">Note</span><span class="sxs-lookup"><span data-stu-id="9ff12-107">Remarks</span></span>  
 <span data-ttu-id="9ff12-108">È possibile chiamare il [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) metodo per determinare se il modulo è stato caricato o scaricato.</span><span class="sxs-lookup"><span data-stu-id="9ff12-108">You can call the [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ff12-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9ff12-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ff12-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9ff12-110">Requirements</span></span>  
 <span data-ttu-id="9ff12-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ff12-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ff12-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="9ff12-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ff12-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ff12-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ff12-114">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ff12-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ff12-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ff12-115">See Also</span></span>  
 [<span data-ttu-id="9ff12-116">Interfaccia ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="9ff12-116">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
 [<span data-ttu-id="9ff12-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9ff12-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
