---
title: Metodo ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f390bced01428f2d94b4cebcc26e1d773bda2191
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64613782"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="2fab6-102">Metodo ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode</span><span class="sxs-lookup"><span data-stu-id="2fab6-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>
<span data-ttu-id="2fab6-103">[Supportato in [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="2fab6-103">[Supported in the [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="2fab6-104">Abilita o disabilita alcuni tipi di [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) callback di eccezione.</span><span class="sxs-lookup"><span data-stu-id="2fab6-104">Enables or disables certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fab6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2fab6-105">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fab6-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="2fab6-106">Parameters</span></span>  
 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="2fab6-107">[in]</span><span class="sxs-lookup"><span data-stu-id="2fab6-107">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2fab6-108">Note</span><span class="sxs-lookup"><span data-stu-id="2fab6-108">Remarks</span></span>  
 <span data-ttu-id="2fab6-109">Se il valore di `enableExceptionsOutsideOfJMC` è `false`:</span><span class="sxs-lookup"><span data-stu-id="2fab6-109">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
- <span data-ttu-id="2fab6-110">Un'eccezione DEBUG_EXCEPTION_FIRST_CHANCE non comporterà un callback al debugger.</span><span class="sxs-lookup"><span data-stu-id="2fab6-110">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
- <span data-ttu-id="2fab6-111">Un'eccezione DEBUG_EXCEPTION_CATCH_HANDLER_FOUND non comporterà un callback al debugger se l'eccezione non ignora mai nel codice utente (vale a dire, il percorso dall'origine di un gestore di eccezioni non ha metodi contrassegnati JustMyCode o JMC).</span><span class="sxs-lookup"><span data-stu-id="2fab6-111">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="2fab6-112">Il valore predefinito di `enableExceptionsOutsideOfJMC` è `true`.</span><span class="sxs-lookup"><span data-stu-id="2fab6-112">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fab6-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2fab6-113">Requirements</span></span>  
 <span data-ttu-id="2fab6-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fab6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fab6-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2fab6-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2fab6-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2fab6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2fab6-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fab6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fab6-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2fab6-118">See also</span></span>

- [<span data-ttu-id="2fab6-119">Interfaccia ICorDebugProcess8</span><span class="sxs-lookup"><span data-stu-id="2fab6-119">ICorDebugProcess8 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)
- [<span data-ttu-id="2fab6-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="2fab6-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
