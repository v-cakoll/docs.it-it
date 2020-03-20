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
ms.openlocfilehash: 3777ad4b12c7d0593c095c470aba81088137a859
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179172"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="e6452-102">Metodo ICLRDataTarget::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="e6452-102">ICLRDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="e6452-103">Ottiene il contesto di esecuzione corrente per il thread specificato nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e6452-103">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="e6452-104">Questo metodo viene chiamato dai servizi di accesso ai dati di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="e6452-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6452-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e6452-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6452-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e6452-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="e6452-107">[in] Identificatore del sistema operativo di un thread nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e6452-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="e6452-108">[in] Flag che specificano le parti del contesto da restituire.</span><span class="sxs-lookup"><span data-stu-id="e6452-108">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="e6452-109">L'implementazione restituirà almeno queste parti del contesto.</span><span class="sxs-lookup"><span data-stu-id="e6452-109">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="e6452-110">[in] Dimensione del contesto.</span><span class="sxs-lookup"><span data-stu-id="e6452-110">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="e6452-111">[fuori] Puntatore a un buffer in cui inserire il contesto.</span><span class="sxs-lookup"><span data-stu-id="e6452-111">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="e6452-112">I dati `context` nel buffer devono essere nel formato `CONTEXT` della struttura Win32.</span><span class="sxs-lookup"><span data-stu-id="e6452-112">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="e6452-113">Il contesto specifica i dati del registro specifici `CONTEXT` del processore, pertanto la definizione della struttura Win32 dipende dall'architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="e6452-113">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="e6452-114">Fare riferimento al file di intestazione WinNT.h `CONTEXT` per la definizione della struttura Win32.</span><span class="sxs-lookup"><span data-stu-id="e6452-114">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6452-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e6452-115">Remarks</span></span>  
 <span data-ttu-id="e6452-116">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="e6452-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6452-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e6452-117">Requirements</span></span>  
 <span data-ttu-id="e6452-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6452-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6452-119">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="e6452-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e6452-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6452-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6452-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6452-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6452-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6452-122">See also</span></span>

- [<span data-ttu-id="e6452-123">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="e6452-123">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
