---
title: Metodo ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: b6bfd258f35f19719be5e5169a1edc22a358371c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123380"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="967d5-102">Metodo ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode</span><span class="sxs-lookup"><span data-stu-id="967d5-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>
<span data-ttu-id="967d5-103">[Supportato in .NET Framework 4,6 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="967d5-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="967d5-104">Abilita o disabilita alcuni tipi di callback di eccezione [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="967d5-104">Enables or disables certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="967d5-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="967d5-105">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="967d5-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="967d5-106">Parameters</span></span>  
 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="967d5-107">[in]</span><span class="sxs-lookup"><span data-stu-id="967d5-107">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="967d5-108">Note</span><span class="sxs-lookup"><span data-stu-id="967d5-108">Remarks</span></span>  
 <span data-ttu-id="967d5-109">Se il valore di `enableExceptionsOutsideOfJMC` è `false`:</span><span class="sxs-lookup"><span data-stu-id="967d5-109">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
- <span data-ttu-id="967d5-110">Un'eccezione DEBUG_EXCEPTION_FIRST_CHANCE non comporterà un callback al debugger.</span><span class="sxs-lookup"><span data-stu-id="967d5-110">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
- <span data-ttu-id="967d5-111">Un'eccezione DEBUG_EXCEPTION_CATCH_HANDLER_FOUND non comporterà un callback al debugger se l'eccezione non viene mai sottoposta a escape nel codice utente, ovvero se il percorso da un'origine di eccezione a un gestore di eccezioni non ha metodi contrassegnati come JustMyCode o JMC.</span><span class="sxs-lookup"><span data-stu-id="967d5-111">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="967d5-112">Il valore predefinito di `enableExceptionsOutsideOfJMC` è `true`.</span><span class="sxs-lookup"><span data-stu-id="967d5-112">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="967d5-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="967d5-113">Requirements</span></span>  
 <span data-ttu-id="967d5-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="967d5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="967d5-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="967d5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="967d5-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="967d5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="967d5-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="967d5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="967d5-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="967d5-118">See also</span></span>

- [<span data-ttu-id="967d5-119">Interfaccia ICorDebugProcess8</span><span class="sxs-lookup"><span data-stu-id="967d5-119">ICorDebugProcess8 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)
- [<span data-ttu-id="967d5-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="967d5-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
