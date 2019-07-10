---
title: Metodo ICLRDataTarget::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetThreadContext
helpviewer_keywords:
- ICLRDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: b9d8c3b5-3a2e-4225-95d4-dd052c4532c3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1492c6d72d68a95a79925d7789a710b5b5ed14b1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738700"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="f5faa-102">Metodo ICLRDataTarget::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="f5faa-102">ICLRDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="f5faa-103">Ottiene il contesto di esecuzione corrente per il thread nel processo di destinazione specificato.</span><span class="sxs-lookup"><span data-stu-id="f5faa-103">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="f5faa-104">Questo metodo viene chiamato dai servizi di accesso dati di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="f5faa-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5faa-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f5faa-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]   
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5faa-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f5faa-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="f5faa-107">[in] L'identificatore del sistema operativo di un thread nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f5faa-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="f5faa-108">[in] Flag che specificano le parti del contesto da restituire.</span><span class="sxs-lookup"><span data-stu-id="f5faa-108">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="f5faa-109">L'implementazione restituisce almeno le parti del contesto.</span><span class="sxs-lookup"><span data-stu-id="f5faa-109">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="f5faa-110">[in] Le dimensioni del contesto.</span><span class="sxs-lookup"><span data-stu-id="f5faa-110">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="f5faa-111">[out] Puntatore a un buffer in cui inserire il contesto.</span><span class="sxs-lookup"><span data-stu-id="f5faa-111">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="f5faa-112">I dati di `context` buffer deve essere nel formato Win32 `CONTEXT` struttura.</span><span class="sxs-lookup"><span data-stu-id="f5faa-112">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="f5faa-113">Il contesto specifica i dati di registro specifico del processore, pertanto la definizione di Win32 `CONTEXT` struttura dipende dall'architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="f5faa-113">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="f5faa-114">Fare riferimento al file di intestazione Winnt. H per la definizione di Win32 `CONTEXT` struttura.</span><span class="sxs-lookup"><span data-stu-id="f5faa-114">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5faa-115">Note</span><span class="sxs-lookup"><span data-stu-id="f5faa-115">Remarks</span></span>  
 <span data-ttu-id="f5faa-116">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="f5faa-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5faa-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f5faa-117">Requirements</span></span>  
 <span data-ttu-id="f5faa-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5faa-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5faa-119">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="f5faa-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="f5faa-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5faa-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5faa-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5faa-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5faa-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5faa-122">See also</span></span>

- [<span data-ttu-id="f5faa-123">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="f5faa-123">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
