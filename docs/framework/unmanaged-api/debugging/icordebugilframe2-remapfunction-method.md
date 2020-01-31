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
ms.openlocfilehash: f4f73b99b4cb48690a2a8611dbf5a5420adab5d4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794349"
---
# <a name="icordebugilframe2remapfunction-method"></a><span data-ttu-id="9d47c-102">Metodo ICorDebugILFrame2::RemapFunction</span><span class="sxs-lookup"><span data-stu-id="9d47c-102">ICorDebugILFrame2::RemapFunction Method</span></span>
<span data-ttu-id="9d47c-103">Consente di rimappare una funzione modificata specificando il nuovo offset MSIL (Microsoft Intermediate Language)</span><span class="sxs-lookup"><span data-stu-id="9d47c-103">Remaps an edited function by specifying the new Microsoft intermediate language (MSIL) offset</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d47c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9d47c-104">Syntax</span></span>  
  
```cpp  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d47c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9d47c-105">Parameters</span></span>  
 `newILOffset`  
 <span data-ttu-id="9d47c-106">in Nuovo offset MSIL del stack frame in corrispondenza del quale deve essere inserito il puntatore all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="9d47c-106">[in] The stack frame's new MSIL offset at which the instruction pointer should be placed.</span></span> <span data-ttu-id="9d47c-107">Questo valore deve essere un punto di sequenza.</span><span class="sxs-lookup"><span data-stu-id="9d47c-107">This value must be a sequence point.</span></span>  
  
 <span data-ttu-id="9d47c-108">È responsabilità del chiamante garantire la validità di questo valore.</span><span class="sxs-lookup"><span data-stu-id="9d47c-108">It is the caller’s responsibility to ensure the validity of this value.</span></span> <span data-ttu-id="9d47c-109">Ad esempio, l'offset MSIL non è valido se non è compreso nei limiti della funzione.</span><span class="sxs-lookup"><span data-stu-id="9d47c-109">For example, the MSIL offset is not valid if it is outside the bounds of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d47c-110">Note</span><span class="sxs-lookup"><span data-stu-id="9d47c-110">Remarks</span></span>  
 <span data-ttu-id="9d47c-111">Quando la funzione di un frame è stata modificata, il debugger può chiamare il metodo `RemapFunction` per scambiare la versione più recente della funzione del frame, in modo che possa essere eseguita.</span><span class="sxs-lookup"><span data-stu-id="9d47c-111">When a frame’s function has been edited, the debugger can call the `RemapFunction` method to swap in the latest version of the frame's function so it can be executed.</span></span> <span data-ttu-id="9d47c-112">L'esecuzione del codice inizierà in corrispondenza dell'offset MSIL specificato.</span><span class="sxs-lookup"><span data-stu-id="9d47c-112">The code execution will begin at the given MSIL offset.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9d47c-113">Se si chiama `RemapFunction`, ad esempio chiamando [ICorDebugILFrame:: SetIP](icordebugilframe-setip-method.md), verranno immediatamente Invalidate tutte le interfacce di debug correlate alla generazione di un'analisi dello stack per il thread.</span><span class="sxs-lookup"><span data-stu-id="9d47c-113">Calling `RemapFunction`, like calling [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md), will immediately invalidate all debugging interfaces that are related to generating a stack trace for the thread.</span></span> <span data-ttu-id="9d47c-114">Queste interfacce includono [ICorDebugChain](icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame e ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="9d47c-114">These interfaces include [ICorDebugChain](icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame, and ICorDebugNativeFrame.</span></span>  
  
 <span data-ttu-id="9d47c-115">Il metodo `RemapFunction` può essere chiamato solo nel contesto del frame corrente e solo in uno dei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d47c-115">The `RemapFunction` method can be called only in the context of the current frame, and only in one of the following cases:</span></span>  
  
- <span data-ttu-id="9d47c-116">Dopo la ricezione di un callback [ICorDebugManagedCallback2:: FunctionRemapOpportunity](icordebugmanagedcallback2-functionremapopportunity-method.md) che non è stato ancora continuato.</span><span class="sxs-lookup"><span data-stu-id="9d47c-116">After receipt of a [ICorDebugManagedCallback2::FunctionRemapOpportunity](icordebugmanagedcallback2-functionremapopportunity-method.md) callback that has not yet been continued.</span></span>  
  
- <span data-ttu-id="9d47c-117">Durante l'esecuzione del codice interrotto a causa di un evento [ICorDebugManagedCallback:: EditAndContinueRemap](icordebugmanagedcallback-editandcontinueremap-method.md) per questo frame.</span><span class="sxs-lookup"><span data-stu-id="9d47c-117">While code execution is stopped because of an [ICorDebugManagedCallback::EditAndContinueRemap](icordebugmanagedcallback-editandcontinueremap-method.md) event for this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d47c-118">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="9d47c-118">Requirements</span></span>  
 <span data-ttu-id="9d47c-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d47c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d47c-120">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d47c-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d47c-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d47c-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d47c-122">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d47c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
