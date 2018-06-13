---
title: Metodo ICorDebugProcess::SetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::SetThreadContext
helpviewer_keywords:
- ICorDebugProcess::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a7b50175-2bf1-40be-8f65-64aec7aa1247
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c9ed79eb799971dfcbc9fd787cd0290795f79d96
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417973"
---
# <a name="icordebugprocesssetthreadcontext-method"></a><span data-ttu-id="4a687-102">Metodo ICorDebugProcess::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="4a687-102">ICorDebugProcess::SetThreadContext Method</span></span>
<span data-ttu-id="4a687-103">Imposta il contesto per il thread specificato in questo processo.</span><span class="sxs-lookup"><span data-stu-id="4a687-103">Sets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a687-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a687-104">Syntax</span></span>  
  
```  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4a687-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4a687-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="4a687-106">[in] L'ID del thread per il quale impostare il contesto.</span><span class="sxs-lookup"><span data-stu-id="4a687-106">[in] The ID of the thread for which to set the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="4a687-107">[in] Dimensione della matrice `context`.</span><span class="sxs-lookup"><span data-stu-id="4a687-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="4a687-108">[in] Matrice di byte che descrivono il contesto del thread.</span><span class="sxs-lookup"><span data-stu-id="4a687-108">[in] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="4a687-109">Il contesto specifica l'architettura del processore in cui il thread è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4a687-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a687-110">Note</span><span class="sxs-lookup"><span data-stu-id="4a687-110">Remarks</span></span>  
 <span data-ttu-id="4a687-111">Il debugger deve chiamare questo metodo anziché Win32 `SetThreadContext` funzionare, perché il thread potrebbe essere in uno stato "fraudolente", in cui è stato temporaneamente modificato il relativo contesto.</span><span class="sxs-lookup"><span data-stu-id="4a687-111">The debugger should call this method rather than the Win32 `SetThreadContext` function, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="4a687-112">Questo metodo deve essere utilizzato solo quando un thread in codice nativo.</span><span class="sxs-lookup"><span data-stu-id="4a687-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="4a687-113">Utilizzare [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) per i thread nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="4a687-113">Use [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) for threads in managed code.</span></span> <span data-ttu-id="4a687-114">Non è necessario modificare il contesto di un thread durante un evento di debug fuori banda (OOB).</span><span class="sxs-lookup"><span data-stu-id="4a687-114">You should never need to modify the context of a thread during an out-of-band (OOB) debug event.</span></span>  
  
 <span data-ttu-id="4a687-115">I dati passati devono essere una struttura di contesto per la piattaforma corrente.</span><span class="sxs-lookup"><span data-stu-id="4a687-115">The data passed must be a context structure for the current platform.</span></span>  
  
 <span data-ttu-id="4a687-116">Questo metodo può danneggiare il runtime, se utilizzato in modo non corretto.</span><span class="sxs-lookup"><span data-stu-id="4a687-116">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a687-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4a687-117">Requirements</span></span>  
 <span data-ttu-id="4a687-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a687-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a687-119">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="4a687-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a687-120">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="4a687-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a687-121">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a687-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
