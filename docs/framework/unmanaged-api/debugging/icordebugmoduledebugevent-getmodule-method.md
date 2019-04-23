---
title: Metodo ICorDebugModuleDebugEvent::GetModule
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c0cc1305f47f03c8c9b35bab5c980cb23d1b157
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59138437"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="884ed-102">Metodo ICorDebugModuleDebugEvent::GetModule</span><span class="sxs-lookup"><span data-stu-id="884ed-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="884ed-103">Ottiene il modulo unito appena caricato o scaricato.</span><span class="sxs-lookup"><span data-stu-id="884ed-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="884ed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="884ed-104">Syntax</span></span>  
  
```  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="884ed-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="884ed-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="884ed-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugModule che rappresenta il modulo unito che è stato appena caricato o scaricato.</span><span class="sxs-lookup"><span data-stu-id="884ed-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="884ed-107">Note</span><span class="sxs-lookup"><span data-stu-id="884ed-107">Remarks</span></span>  
 <span data-ttu-id="884ed-108">È possibile chiamare il [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) metodo per determinare se il modulo è stato caricato o scaricato.</span><span class="sxs-lookup"><span data-stu-id="884ed-108">You can call the [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="884ed-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="884ed-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="884ed-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="884ed-110">Requirements</span></span>  
 <span data-ttu-id="884ed-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="884ed-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="884ed-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="884ed-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="884ed-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="884ed-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="884ed-114">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="884ed-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="884ed-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="884ed-115">See also</span></span>

- [<span data-ttu-id="884ed-116">Interfaccia ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="884ed-116">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="884ed-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="884ed-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
