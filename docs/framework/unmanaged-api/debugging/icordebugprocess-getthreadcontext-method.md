---
title: Metodo ICorDebugProcess::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThreadContext
helpviewer_keywords:
- ICorDebugProcess::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: 5b132ef1-8d4b-4525-89b3-54123596c194
topic_type:
- apiref
ms.openlocfilehash: 2bdbf373144e2fb49074cfd035e7b0ffe3c8c291
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212888"
---
# <a name="icordebugprocessgetthreadcontext-method"></a><span data-ttu-id="3f545-102">Metodo ICorDebugProcess::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="3f545-102">ICorDebugProcess::GetThreadContext Method</span></span>
<span data-ttu-id="3f545-103">Ottiene il contesto per il thread specificato in questo processo.</span><span class="sxs-lookup"><span data-stu-id="3f545-103">Gets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f545-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f545-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f545-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3f545-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="3f545-106">in ID del thread per il quale recuperare il contesto.</span><span class="sxs-lookup"><span data-stu-id="3f545-106">[in] The ID of the thread for which to retrieve the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="3f545-107">[in] Dimensione della matrice `context`.</span><span class="sxs-lookup"><span data-stu-id="3f545-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="3f545-108">[in, out] Matrice di byte che descrivono il contesto del thread.</span><span class="sxs-lookup"><span data-stu-id="3f545-108">[in, out] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="3f545-109">Il contesto specifica l'architettura del processore in cui è in esecuzione il thread.</span><span class="sxs-lookup"><span data-stu-id="3f545-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f545-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3f545-110">Remarks</span></span>  
 <span data-ttu-id="3f545-111">Il debugger deve chiamare questo metodo anziché il metodo Win32 `GetThreadContext` , perché il thread può effettivamente trovarsi in uno stato di "Hijack", in cui il contesto è stato modificato temporaneamente.</span><span class="sxs-lookup"><span data-stu-id="3f545-111">The debugger should call this method rather than the Win32 `GetThreadContext` method, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="3f545-112">Questo metodo deve essere utilizzato solo quando un thread è in codice nativo.</span><span class="sxs-lookup"><span data-stu-id="3f545-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="3f545-113">Usare [ICorDebugRegisterSet](icordebugregisterset-interface.md) per i thread nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="3f545-113">Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) for threads in managed code.</span></span>  
  
 <span data-ttu-id="3f545-114">I dati restituiti sono una struttura di contesto per la piattaforma corrente.</span><span class="sxs-lookup"><span data-stu-id="3f545-114">The data returned is a context structure for the current platform.</span></span> <span data-ttu-id="3f545-115">Analogamente al metodo Win32 `GetThreadContext` , il chiamante deve inizializzare il `context` parametro prima di chiamare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="3f545-115">Just as with the Win32 `GetThreadContext` method, the caller should initialize the `context` parameter before calling this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f545-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3f545-116">Requirements</span></span>  
 <span data-ttu-id="3f545-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f545-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f545-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f545-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f545-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f545-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f545-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f545-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
