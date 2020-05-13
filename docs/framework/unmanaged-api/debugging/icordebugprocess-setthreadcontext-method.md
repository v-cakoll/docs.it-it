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
ms.openlocfilehash: c9e403dc8cbb75a1e93c426a9e0b3a2083f1f10e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210462"
---
# <a name="icordebugprocesssetthreadcontext-method"></a><span data-ttu-id="c3740-102">Metodo ICorDebugProcess::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="c3740-102">ICorDebugProcess::SetThreadContext Method</span></span>
<span data-ttu-id="c3740-103">Imposta il contesto per il thread specificato in questo processo.</span><span class="sxs-lookup"><span data-stu-id="c3740-103">Sets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3740-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3740-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3740-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c3740-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="c3740-106">in ID del thread per il quale impostare il contesto.</span><span class="sxs-lookup"><span data-stu-id="c3740-106">[in] The ID of the thread for which to set the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="c3740-107">[in] Dimensione della matrice `context`.</span><span class="sxs-lookup"><span data-stu-id="c3740-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="c3740-108">in Matrice di byte che descrivono il contesto del thread.</span><span class="sxs-lookup"><span data-stu-id="c3740-108">[in] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="c3740-109">Il contesto specifica l'architettura del processore in cui è in esecuzione il thread.</span><span class="sxs-lookup"><span data-stu-id="c3740-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3740-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c3740-110">Remarks</span></span>  
 <span data-ttu-id="c3740-111">Il debugger deve chiamare questo metodo anziché la funzione Win32 `SetThreadContext` , perché il thread può effettivamente trovarsi in uno stato di "Hijack", in cui il contesto è stato modificato temporaneamente.</span><span class="sxs-lookup"><span data-stu-id="c3740-111">The debugger should call this method rather than the Win32 `SetThreadContext` function, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="c3740-112">Questo metodo deve essere utilizzato solo quando un thread è in codice nativo.</span><span class="sxs-lookup"><span data-stu-id="c3740-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="c3740-113">Usare [ICorDebugRegisterSet](icordebugregisterset-interface.md) per i thread nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="c3740-113">Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) for threads in managed code.</span></span> <span data-ttu-id="c3740-114">Non è mai necessario modificare il contesto di un thread durante un evento di debug fuori banda (OOB).</span><span class="sxs-lookup"><span data-stu-id="c3740-114">You should never need to modify the context of a thread during an out-of-band (OOB) debug event.</span></span>  
  
 <span data-ttu-id="c3740-115">I dati passati devono essere una struttura di contesto per la piattaforma corrente.</span><span class="sxs-lookup"><span data-stu-id="c3740-115">The data passed must be a context structure for the current platform.</span></span>  
  
 <span data-ttu-id="c3740-116">Questo metodo può danneggiare il runtime se usato in modo errato.</span><span class="sxs-lookup"><span data-stu-id="c3740-116">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3740-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c3740-117">Requirements</span></span>  
 <span data-ttu-id="c3740-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3740-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3740-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3740-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3740-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3740-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3740-121">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3740-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
