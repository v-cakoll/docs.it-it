---
title: Metodo ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: 2c0da899b3f6f3c229c6f5e5b4cafe48fdc19742
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792162"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="89a55-102">Metodo ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode</span><span class="sxs-lookup"><span data-stu-id="89a55-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>
<span data-ttu-id="89a55-103">[Supportato in .NET Framework 4,6 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="89a55-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="89a55-104">Abilita o disabilita alcuni tipi di callback di eccezione [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="89a55-104">Enables or disables certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89a55-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89a55-105">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89a55-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="89a55-106">Parameters</span></span>  
 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="89a55-107">[in]</span><span class="sxs-lookup"><span data-stu-id="89a55-107">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89a55-108">Note</span><span class="sxs-lookup"><span data-stu-id="89a55-108">Remarks</span></span>  
 <span data-ttu-id="89a55-109">Se il valore di `enableExceptionsOutsideOfJMC` è `false`:</span><span class="sxs-lookup"><span data-stu-id="89a55-109">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
- <span data-ttu-id="89a55-110">Un'eccezione DEBUG_EXCEPTION_FIRST_CHANCE non darà luogo a un callback al debugger.</span><span class="sxs-lookup"><span data-stu-id="89a55-110">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
- <span data-ttu-id="89a55-111">Un'eccezione DEBUG_EXCEPTION_CATCH_HANDLER_FOUND darà luogo a un callback al debugger se l'eccezione non raggiunge mai il codice utente (ovvero, il percorso dall'origine di un'eccezione a un gestore di eccezioni non ha metodi contrassegnati JustMyCode o JMC).</span><span class="sxs-lookup"><span data-stu-id="89a55-111">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="89a55-112">Il valore predefinito di `enableExceptionsOutsideOfJMC` è `true`.</span><span class="sxs-lookup"><span data-stu-id="89a55-112">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89a55-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="89a55-113">Requirements</span></span>  
 <span data-ttu-id="89a55-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89a55-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89a55-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89a55-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89a55-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89a55-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89a55-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89a55-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89a55-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89a55-118">See also</span></span>

- [<span data-ttu-id="89a55-119">Interfaccia ICorDebugProcess8</span><span class="sxs-lookup"><span data-stu-id="89a55-119">ICorDebugProcess8 Interface</span></span>](icordebugprocess8-interface.md)
- [<span data-ttu-id="89a55-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="89a55-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
