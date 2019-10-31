---
title: Metodo ICorDebugILFrame2::RemapFunction
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.RemapFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::RemapFunction
helpviewer_keywords:
- ICorDebugILFrame2::RemapFunction method [.NET Framework debugging]
- RemapFunction method [.NET Framework debugging]
ms.assetid: dd639ba0-f77b-426d-9ff6-f92706840348
topic_type:
- apiref
ms.openlocfilehash: 152cdb13a9f517a7a9c29c04a056661bb2edb45e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090448"
---
# <a name="icordebugilframe2remapfunction-method"></a><span data-ttu-id="f243f-102">Metodo ICorDebugILFrame2::RemapFunction</span><span class="sxs-lookup"><span data-stu-id="f243f-102">ICorDebugILFrame2::RemapFunction Method</span></span>
<span data-ttu-id="f243f-103">Consente di rimappare una funzione modificata specificando il nuovo offset MSIL (Microsoft Intermediate Language)</span><span class="sxs-lookup"><span data-stu-id="f243f-103">Remaps an edited function by specifying the new Microsoft intermediate language (MSIL) offset</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f243f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f243f-104">Syntax</span></span>  
  
```cpp  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f243f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f243f-105">Parameters</span></span>  
 `newILOffset`  
 <span data-ttu-id="f243f-106">in Nuovo offset MSIL del stack frame in corrispondenza del quale deve essere inserito il puntatore all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="f243f-106">[in] The stack frame's new MSIL offset at which the instruction pointer should be placed.</span></span> <span data-ttu-id="f243f-107">Questo valore deve essere un punto di sequenza.</span><span class="sxs-lookup"><span data-stu-id="f243f-107">This value must be a sequence point.</span></span>  
  
 <span data-ttu-id="f243f-108">È responsabilità del chiamante garantire la validità di questo valore.</span><span class="sxs-lookup"><span data-stu-id="f243f-108">It is the caller’s responsibility to ensure the validity of this value.</span></span> <span data-ttu-id="f243f-109">Ad esempio, l'offset MSIL non è valido se non è compreso nei limiti della funzione.</span><span class="sxs-lookup"><span data-stu-id="f243f-109">For example, the MSIL offset is not valid if it is outside the bounds of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f243f-110">Note</span><span class="sxs-lookup"><span data-stu-id="f243f-110">Remarks</span></span>  
 <span data-ttu-id="f243f-111">Quando la funzione di un frame è stata modificata, il debugger può chiamare il metodo `RemapFunction` per scambiare la versione più recente della funzione del frame, in modo che possa essere eseguita.</span><span class="sxs-lookup"><span data-stu-id="f243f-111">When a frame’s function has been edited, the debugger can call the `RemapFunction` method to swap in the latest version of the frame's function so it can be executed.</span></span> <span data-ttu-id="f243f-112">L'esecuzione del codice inizierà in corrispondenza dell'offset MSIL specificato.</span><span class="sxs-lookup"><span data-stu-id="f243f-112">The code execution will begin at the given MSIL offset.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f243f-113">Se si chiama `RemapFunction`, ad esempio chiamando [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), verranno immediatamente Invalidate tutte le interfacce di debug correlate alla generazione di un'analisi dello stack per il thread.</span><span class="sxs-lookup"><span data-stu-id="f243f-113">Calling `RemapFunction`, like calling [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), will immediately invalidate all debugging interfaces that are related to generating a stack trace for the thread.</span></span> <span data-ttu-id="f243f-114">Queste interfacce includono [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame e ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="f243f-114">These interfaces include [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame, and ICorDebugNativeFrame.</span></span>  
  
 <span data-ttu-id="f243f-115">Il metodo `RemapFunction` può essere chiamato solo nel contesto del frame corrente e solo in uno dei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f243f-115">The `RemapFunction` method can be called only in the context of the current frame, and only in one of the following cases:</span></span>  
  
- <span data-ttu-id="f243f-116">Dopo la ricezione di un callback [ICorDebugManagedCallback2:: FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) che non è stato ancora continuato.</span><span class="sxs-lookup"><span data-stu-id="f243f-116">After receipt of a [ICorDebugManagedCallback2::FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) callback that has not yet been continued.</span></span>  
  
- <span data-ttu-id="f243f-117">Durante l'esecuzione del codice interrotto a causa di un evento [ICorDebugManagedCallback:: EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) per questo frame.</span><span class="sxs-lookup"><span data-stu-id="f243f-117">While code execution is stopped because of an [ICorDebugManagedCallback::EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) event for this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f243f-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f243f-118">Requirements</span></span>  
 <span data-ttu-id="f243f-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f243f-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f243f-120">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f243f-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f243f-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f243f-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f243f-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f243f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
