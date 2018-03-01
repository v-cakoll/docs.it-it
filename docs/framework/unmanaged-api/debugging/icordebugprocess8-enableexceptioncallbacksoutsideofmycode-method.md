---
title: Metodo ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3f13236c865f9a57d77ebf83ab48e010f06ef08e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="4121c-102">Metodo ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode</span><span class="sxs-lookup"><span data-stu-id="4121c-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>
<span data-ttu-id="4121c-103">[Supportato in [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="4121c-103">[Supported in the [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="4121c-104">Abilita o disabilita alcuni tipi di [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) callback di eccezione.</span><span class="sxs-lookup"><span data-stu-id="4121c-104">Enables or disables certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4121c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4121c-105">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4121c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="4121c-106">Parameters</span></span>  
 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="4121c-107">[in]</span><span class="sxs-lookup"><span data-stu-id="4121c-107">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4121c-108">Note</span><span class="sxs-lookup"><span data-stu-id="4121c-108">Remarks</span></span>  
 <span data-ttu-id="4121c-109">Se il valore di `enableExceptionsOutsideOfJMC` è `false`:</span><span class="sxs-lookup"><span data-stu-id="4121c-109">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
-   <span data-ttu-id="4121c-110">Un'eccezione DEBUG_EXCEPTION_FIRST_CHANCE non comporterà un callback al debugger.</span><span class="sxs-lookup"><span data-stu-id="4121c-110">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
-   <span data-ttu-id="4121c-111">Un'eccezione DEBUG_EXCEPTION_CATCH_HANDLER_FOUND non comporterà un callback al debugger se l'eccezione non raggiunge mai il codice utente (ovvero, il percorso dall'origine di un gestore di eccezioni non ha metodi contrassegnati JustMyCode o JMC).</span><span class="sxs-lookup"><span data-stu-id="4121c-111">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="4121c-112">Il valore predefinito di `enableExceptionsOutsideOfJMC` è `true`.</span><span class="sxs-lookup"><span data-stu-id="4121c-112">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4121c-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4121c-113">Requirements</span></span>  
 <span data-ttu-id="4121c-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4121c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4121c-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="4121c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4121c-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4121c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4121c-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4121c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4121c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4121c-118">See Also</span></span>  
 [<span data-ttu-id="4121c-119">Interfaccia ICorDebugProcess8</span><span class="sxs-lookup"><span data-stu-id="4121c-119">ICorDebugProcess8 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)  
 [<span data-ttu-id="4121c-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4121c-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
