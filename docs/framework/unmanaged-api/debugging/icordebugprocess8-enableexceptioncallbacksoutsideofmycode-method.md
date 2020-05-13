---
title: Metodo ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: e54dd051f0dbd9c1964d381c2e05189c375fa66d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210137"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="f67cd-102">Metodo ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode</span><span class="sxs-lookup"><span data-stu-id="f67cd-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>
<span data-ttu-id="f67cd-103">[Supportato in .NET Framework 4,6 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="f67cd-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="f67cd-104">Abilita o disabilita alcuni tipi di callback di eccezione [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="f67cd-104">Enables or disables certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f67cd-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f67cd-105">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f67cd-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f67cd-106">Parameters</span></span>  
 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="f67cd-107">[in]</span><span class="sxs-lookup"><span data-stu-id="f67cd-107">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f67cd-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f67cd-108">Remarks</span></span>  
 <span data-ttu-id="f67cd-109">Se il valore di `enableExceptionsOutsideOfJMC` è `false`:</span><span class="sxs-lookup"><span data-stu-id="f67cd-109">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
- <span data-ttu-id="f67cd-110">Un'eccezione DEBUG_EXCEPTION_FIRST_CHANCE non darà luogo a un callback al debugger.</span><span class="sxs-lookup"><span data-stu-id="f67cd-110">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
- <span data-ttu-id="f67cd-111">Un'eccezione DEBUG_EXCEPTION_CATCH_HANDLER_FOUND darà luogo a un callback al debugger se l'eccezione non raggiunge mai il codice utente (ovvero, il percorso dall'origine di un'eccezione a un gestore di eccezioni non ha metodi contrassegnati JustMyCode o JMC).</span><span class="sxs-lookup"><span data-stu-id="f67cd-111">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="f67cd-112">Il valore predefinito di `enableExceptionsOutsideOfJMC` è `true`.</span><span class="sxs-lookup"><span data-stu-id="f67cd-112">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f67cd-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f67cd-113">Requirements</span></span>  
 <span data-ttu-id="f67cd-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f67cd-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f67cd-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f67cd-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f67cd-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f67cd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f67cd-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f67cd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f67cd-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f67cd-118">See also</span></span>

- [<span data-ttu-id="f67cd-119">Interfaccia ICorDebugProcess8</span><span class="sxs-lookup"><span data-stu-id="f67cd-119">ICorDebugProcess8 Interface</span></span>](icordebugprocess8-interface.md)
- [<span data-ttu-id="f67cd-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f67cd-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
