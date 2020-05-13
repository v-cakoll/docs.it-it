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
ms.openlocfilehash: 786c0e7b38c74fd02dd6f7536af1899f295b0305
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206447"
---
# <a name="icordebugnativeframesetip-method"></a><span data-ttu-id="40921-102">Metodo ICorDebugNativeFrame::SetIP</span><span class="sxs-lookup"><span data-stu-id="40921-102">ICorDebugNativeFrame::SetIP Method</span></span>
<span data-ttu-id="40921-103">Imposta il puntatore all'istruzione per la posizione di offset specificata nel codice nativo.</span><span class="sxs-lookup"><span data-stu-id="40921-103">Sets the instruction pointer to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40921-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="40921-104">Syntax</span></span>  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40921-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="40921-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="40921-106">in Posizione dell'offset nel codice nativo.</span><span class="sxs-lookup"><span data-stu-id="40921-106">[in] The offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40921-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="40921-107">Remarks</span></span>  
 <span data-ttu-id="40921-108">Chiama per `SetIP` invalidare immediatamente tutti i frame e le catene per il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="40921-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="40921-109">Se il debugger necessita di informazioni sul frame dopo una chiamata a `SetIP` , deve eseguire una nuova analisi dello stack.</span><span class="sxs-lookup"><span data-stu-id="40921-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="40921-110">[ICorDebug](icordebug-interface.md) tenterà di impedire la stack frame in uno stato valido.</span><span class="sxs-lookup"><span data-stu-id="40921-110">[ICorDebug](icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="40921-111">Tuttavia, anche se il frame è in uno stato valido, per quanto riguarda il runtime, è possibile che si verifichino problemi, ad esempio le variabili locali non inizializzate e così via.</span><span class="sxs-lookup"><span data-stu-id="40921-111">However, even if the frame is in a valid state, as far as the runtime is concerned, there still may be problems, such as uninitialized local variables, and so on.</span></span> <span data-ttu-id="40921-112">Il chiamante è responsabile dell'assicurazione del coerenza del programma in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="40921-112">The caller is responsible for insuring coherency of the running program.</span></span>  
  
 <span data-ttu-id="40921-113">Sulle piattaforme a 64 bit, il puntatore all'istruzione non può essere spostato all'esterno di un `catch` `finally` blocco o.</span><span class="sxs-lookup"><span data-stu-id="40921-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="40921-114">Se `SetIP` viene chiamato per eseguire tale spostamento su una piattaforma a 64 bit, viene restituito un valore HRESULT che indica un errore.</span><span class="sxs-lookup"><span data-stu-id="40921-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40921-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="40921-115">Requirements</span></span>  
 <span data-ttu-id="40921-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40921-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40921-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40921-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40921-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40921-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40921-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40921-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40921-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40921-120">See also</span></span>
