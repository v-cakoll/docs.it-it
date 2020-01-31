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
ms.openlocfilehash: b5f6a830cbe601443f03cd91a356c7e49450e7f3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793722"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="3245d-102">Metodo ICLRDataTarget::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="3245d-102">ICLRDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="3245d-103">Ottiene il contesto di esecuzione corrente per il thread specificato nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3245d-103">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="3245d-104">Questo metodo viene chiamato dal servizio di accesso ai dati Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="3245d-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3245d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3245d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]   
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3245d-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="3245d-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="3245d-107">in Identificatore del sistema operativo di un thread nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3245d-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="3245d-108">in Flag che specificano le parti del contesto da restituire.</span><span class="sxs-lookup"><span data-stu-id="3245d-108">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="3245d-109">L'implementazione restituirà almeno queste parti del contesto.</span><span class="sxs-lookup"><span data-stu-id="3245d-109">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="3245d-110">in Dimensioni del contesto.</span><span class="sxs-lookup"><span data-stu-id="3245d-110">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="3245d-111">out Puntatore a un buffer in cui inserire il contesto.</span><span class="sxs-lookup"><span data-stu-id="3245d-111">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="3245d-112">I dati nel buffer di `context` devono essere nel formato della struttura di `CONTEXT` Win32.</span><span class="sxs-lookup"><span data-stu-id="3245d-112">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="3245d-113">Il contesto specifica i dati del registro specifici del processore, pertanto la definizione della struttura Win32 `CONTEXT` dipende dall'architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="3245d-113">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="3245d-114">Fare riferimento al file di intestazione WinNT. h per la definizione della struttura `CONTEXT` di Win32.</span><span class="sxs-lookup"><span data-stu-id="3245d-114">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3245d-115">Note</span><span class="sxs-lookup"><span data-stu-id="3245d-115">Remarks</span></span>  
 <span data-ttu-id="3245d-116">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="3245d-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3245d-117">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="3245d-117">Requirements</span></span>  
 <span data-ttu-id="3245d-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3245d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3245d-119">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="3245d-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="3245d-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3245d-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3245d-121">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3245d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3245d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3245d-122">See also</span></span>

- [<span data-ttu-id="3245d-123">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="3245d-123">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
