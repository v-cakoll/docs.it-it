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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f03d8c993be1ac83ca84275bcb94f1bb3cdf884
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414983"
---
# <a name="icordebugilframe2remapfunction-method"></a><span data-ttu-id="73518-102">Metodo ICorDebugILFrame2::RemapFunction</span><span class="sxs-lookup"><span data-stu-id="73518-102">ICorDebugILFrame2::RemapFunction Method</span></span>
<span data-ttu-id="73518-103">Riesegue il mapping di una funzione modificata specificando il nuovo offset di Microsoft intermediate language (MSIL)</span><span class="sxs-lookup"><span data-stu-id="73518-103">Remaps an edited function by specifying the new Microsoft intermediate language (MSIL) offset</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73518-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="73518-104">Syntax</span></span>  
  
```  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="73518-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="73518-105">Parameters</span></span>  
 `newILOffset`  
 <span data-ttu-id="73518-106">[in] Nuovo offset MSIL dello stack frame in corrispondenza del quale deve essere posizionato il puntatore all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="73518-106">[in] The stack frame's new MSIL offset at which the instruction pointer should be placed.</span></span> <span data-ttu-id="73518-107">Questo valore deve essere un punto di sequenza.</span><span class="sxs-lookup"><span data-stu-id="73518-107">This value must be a sequence point.</span></span>  
  
 <span data-ttu-id="73518-108">È responsabilità del chiamante per garantire la validità di questo valore.</span><span class="sxs-lookup"><span data-stu-id="73518-108">It is the caller’s responsibility to ensure the validity of this value.</span></span> <span data-ttu-id="73518-109">Ad esempio, l'offset MSIL non è valido se è presente all'esterno dei limiti della funzione.</span><span class="sxs-lookup"><span data-stu-id="73518-109">For example, the MSIL offset is not valid if it is outside the bounds of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73518-110">Note</span><span class="sxs-lookup"><span data-stu-id="73518-110">Remarks</span></span>  
 <span data-ttu-id="73518-111">Funzione di una cornice è stata modificata, il debugger può chiamare il `RemapFunction` metodo per passare alla versione più recente della funzione del frame in modo da poter essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="73518-111">When a frame’s function has been edited, the debugger can call the `RemapFunction` method to swap in the latest version of the frame's function so it can be executed.</span></span> <span data-ttu-id="73518-112">L'esecuzione del codice inizierà in corrispondenza dell'offset MSIL specificato.</span><span class="sxs-lookup"><span data-stu-id="73518-112">The code execution will begin at the given MSIL offset.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73518-113">La chiamata `RemapFunction`, ad esempio la chiamata [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), invaliderà immediatamente tutte le interfacce di debug che relative alla generazione di una traccia dello stack per il thread.</span><span class="sxs-lookup"><span data-stu-id="73518-113">Calling `RemapFunction`, like calling [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), will immediately invalidate all debugging interfaces that are related to generating a stack trace for the thread.</span></span> <span data-ttu-id="73518-114">Tali interfacce includono [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame e ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="73518-114">These interfaces include [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame, and ICorDebugNativeFrame.</span></span>  
  
 <span data-ttu-id="73518-115">Il `RemapFunction` metodo può essere chiamato solo nel contesto del frame corrente e solo in uno dei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="73518-115">The `RemapFunction` method can be called only in the context of the current frame, and only in one of the following cases:</span></span>  
  
-   <span data-ttu-id="73518-116">Dopo la ricezione di un [ICorDebugManagedCallback2:: FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) callback che non è ancora continuata l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="73518-116">After receipt of a [ICorDebugManagedCallback2::FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) callback that has not yet been continued.</span></span>  
  
-   <span data-ttu-id="73518-117">Durante l'esecuzione di codice viene interrotta a causa di un [ICorDebugManagedCallback:: EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) evento per questo frame.</span><span class="sxs-lookup"><span data-stu-id="73518-117">While code execution is stopped because of an [ICorDebugManagedCallback::EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) event for this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73518-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="73518-118">Requirements</span></span>  
 <span data-ttu-id="73518-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73518-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73518-120">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="73518-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73518-121">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="73518-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73518-122">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73518-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
