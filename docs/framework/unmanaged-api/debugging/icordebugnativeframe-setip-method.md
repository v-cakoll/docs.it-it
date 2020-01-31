---
title: Metodo ICorDebugNativeFrame::SetIP
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::SetIP
helpviewer_keywords:
- ICorDebugNativeFrame::SetIP method [.NET Framework debugging]
- SetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 57784a51-c76d-48f8-9392-584d0e1946d9
topic_type:
- apiref
ms.openlocfilehash: bc33768e4155a0e272d3374d4c586c79ef2ff3fb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792776"
---
# <a name="icordebugnativeframesetip-method"></a><span data-ttu-id="f1f68-102">Metodo ICorDebugNativeFrame::SetIP</span><span class="sxs-lookup"><span data-stu-id="f1f68-102">ICorDebugNativeFrame::SetIP Method</span></span>
<span data-ttu-id="f1f68-103">Imposta il puntatore all'istruzione per la posizione di offset specificata nel codice nativo.</span><span class="sxs-lookup"><span data-stu-id="f1f68-103">Sets the instruction pointer to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1f68-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1f68-104">Syntax</span></span>  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1f68-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f1f68-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="f1f68-106">in Posizione dell'offset nel codice nativo.</span><span class="sxs-lookup"><span data-stu-id="f1f68-106">[in] The offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1f68-107">Note</span><span class="sxs-lookup"><span data-stu-id="f1f68-107">Remarks</span></span>  
 <span data-ttu-id="f1f68-108">Le chiamate a `SetIP` invalidano immediatamente tutti i frame e le catene per il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="f1f68-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="f1f68-109">Se il debugger necessita di informazioni sul frame dopo una chiamata a `SetIP`, deve eseguire una nuova analisi dello stack.</span><span class="sxs-lookup"><span data-stu-id="f1f68-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="f1f68-110">[ICorDebug](icordebug-interface.md) tenterà di impedire la stack frame in uno stato valido.</span><span class="sxs-lookup"><span data-stu-id="f1f68-110">[ICorDebug](icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="f1f68-111">Tuttavia, anche se il frame è in uno stato valido, per quanto riguarda il runtime, è possibile che si verifichino problemi, ad esempio le variabili locali non inizializzate e così via.</span><span class="sxs-lookup"><span data-stu-id="f1f68-111">However, even if the frame is in a valid state, as far as the runtime is concerned, there still may be problems, such as uninitialized local variables, and so on.</span></span> <span data-ttu-id="f1f68-112">Il chiamante è responsabile dell'assicurazione del coerenza del programma in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f1f68-112">The caller is responsible for insuring coherency of the running program.</span></span>  
  
 <span data-ttu-id="f1f68-113">Nelle piattaforme a 64 bit il puntatore all'istruzione non può essere spostato all'esterno di un blocco `catch` o `finally`.</span><span class="sxs-lookup"><span data-stu-id="f1f68-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="f1f68-114">Se `SetIP` viene chiamato per eseguire tale spostamento su una piattaforma a 64 bit, viene restituito un valore HRESULT che indica un errore.</span><span class="sxs-lookup"><span data-stu-id="f1f68-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1f68-115">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="f1f68-115">Requirements</span></span>  
 <span data-ttu-id="f1f68-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1f68-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1f68-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1f68-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1f68-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1f68-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1f68-119">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1f68-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1f68-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1f68-120">See also</span></span>
