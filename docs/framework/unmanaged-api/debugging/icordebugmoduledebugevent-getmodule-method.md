---
title: Metodo ICorDebugModuleDebugEvent::GetModule
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: debf2e9dd08f6a35801932b22fbd985e7299b79f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764354"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="89d02-102">Metodo ICorDebugModuleDebugEvent::GetModule</span><span class="sxs-lookup"><span data-stu-id="89d02-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="89d02-103">Ottiene il modulo unito appena caricato o scaricato.</span><span class="sxs-lookup"><span data-stu-id="89d02-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89d02-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89d02-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89d02-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="89d02-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="89d02-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugModule che rappresenta il modulo unito che è stato appena caricato o scaricato.</span><span class="sxs-lookup"><span data-stu-id="89d02-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89d02-107">Note</span><span class="sxs-lookup"><span data-stu-id="89d02-107">Remarks</span></span>  
 <span data-ttu-id="89d02-108">È possibile chiamare il [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) metodo per determinare se il modulo è stato caricato o scaricato.</span><span class="sxs-lookup"><span data-stu-id="89d02-108">You can call the [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89d02-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="89d02-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89d02-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="89d02-110">Requirements</span></span>  
 <span data-ttu-id="89d02-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89d02-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89d02-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89d02-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89d02-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89d02-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89d02-114">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89d02-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89d02-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89d02-115">See also</span></span>

- [<span data-ttu-id="89d02-116">Interfaccia ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="89d02-116">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="89d02-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="89d02-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
