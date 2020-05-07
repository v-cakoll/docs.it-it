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
ms.openlocfilehash: 5c0fb023dd355f3a9c1ed846913f86b354592ed5
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860602"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="34a71-102">Metodo ICLRDataTarget::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="34a71-102">ICLRDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="34a71-103">Ottiene il contesto di esecuzione corrente per il thread specificato nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="34a71-103">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="34a71-104">Questo metodo viene chiamato dal servizio di accesso ai dati Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="34a71-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34a71-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34a71-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34a71-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="34a71-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="34a71-107">in Identificatore del sistema operativo di un thread nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="34a71-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="34a71-108">in Flag che specificano le parti del contesto da restituire.</span><span class="sxs-lookup"><span data-stu-id="34a71-108">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="34a71-109">L'implementazione restituirà almeno queste parti del contesto.</span><span class="sxs-lookup"><span data-stu-id="34a71-109">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="34a71-110">in Dimensioni del contesto.</span><span class="sxs-lookup"><span data-stu-id="34a71-110">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="34a71-111">out Puntatore a un buffer in cui inserire il contesto.</span><span class="sxs-lookup"><span data-stu-id="34a71-111">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="34a71-112">I dati nel `context` buffer devono essere nel formato della struttura Win32 `CONTEXT` .</span><span class="sxs-lookup"><span data-stu-id="34a71-112">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="34a71-113">Il contesto specifica i dati del registro specifici del processore, pertanto la definizione della `CONTEXT` struttura Win32 dipende dall'architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="34a71-113">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="34a71-114">Per la definizione della struttura Win32 `CONTEXT` , fare riferimento al file di intestazione Winnt. h.</span><span class="sxs-lookup"><span data-stu-id="34a71-114">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34a71-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="34a71-115">Remarks</span></span>  
 <span data-ttu-id="34a71-116">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="34a71-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34a71-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="34a71-117">Requirements</span></span>  
 <span data-ttu-id="34a71-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34a71-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34a71-119">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="34a71-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="34a71-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34a71-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34a71-121">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34a71-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34a71-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34a71-122">See also</span></span>

- [<span data-ttu-id="34a71-123">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="34a71-123">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
