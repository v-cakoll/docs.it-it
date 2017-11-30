---
title: Metodo ICLRDataTarget::GetThreadContext
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.GetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::GetThreadContext
helpviewer_keywords:
- ICLRDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: b9d8c3b5-3a2e-4225-95d4-dd052c4532c3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 480b65b279dbc0359b078f3f1d543f63a0bfd0f6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="440d0-102">Metodo ICLRDataTarget::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="440d0-102">ICLRDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="440d0-103">Ottiene il contesto di esecuzione corrente per il thread nel processo di destinazione specificato.</span><span class="sxs-lookup"><span data-stu-id="440d0-103">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="440d0-104">Questo metodo viene chiamato dai servizi di accesso dati di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="440d0-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="440d0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="440d0-105">Syntax</span></span>  
  
```  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]   
        BYTE                *context  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="440d0-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="440d0-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="440d0-107">[in] Identificatore del sistema operativo di un thread nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="440d0-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="440d0-108">[in] Flag che specificano le parti del contesto da restituire.</span><span class="sxs-lookup"><span data-stu-id="440d0-108">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="440d0-109">L'implementazione restituirà almeno le parti del contesto.</span><span class="sxs-lookup"><span data-stu-id="440d0-109">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="440d0-110">[in] Le dimensioni del contesto.</span><span class="sxs-lookup"><span data-stu-id="440d0-110">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="440d0-111">[out] Puntatore a un buffer in cui inserire il contesto.</span><span class="sxs-lookup"><span data-stu-id="440d0-111">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="440d0-112">I dati di `context` buffer deve essere nel formato Win32 `CONTEXT` struttura.</span><span class="sxs-lookup"><span data-stu-id="440d0-112">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="440d0-113">Il contesto specifica i dati di registro specifici, la definizione di Win32 `CONTEXT` struttura dipende dall'architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="440d0-113">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="440d0-114">Fare riferimento al file di intestazione Winnt. H per la definizione dell'oggetto Win32 `CONTEXT` struttura.</span><span class="sxs-lookup"><span data-stu-id="440d0-114">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="440d0-115">Note</span><span class="sxs-lookup"><span data-stu-id="440d0-115">Remarks</span></span>  
 <span data-ttu-id="440d0-116">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="440d0-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="440d0-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="440d0-117">Requirements</span></span>  
 <span data-ttu-id="440d0-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="440d0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="440d0-119">**Intestazione:** ClrData.idl, Clrdata. H</span><span class="sxs-lookup"><span data-stu-id="440d0-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="440d0-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="440d0-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="440d0-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="440d0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="440d0-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="440d0-122">See Also</span></span>  
 [<span data-ttu-id="440d0-123">ICLRDataTarget (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="440d0-123">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
