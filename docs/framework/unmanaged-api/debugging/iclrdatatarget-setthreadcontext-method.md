---
title: Metodo ICLRDataTarget::SetThreadContext
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetThreadContext
helpviewer_keywords:
- SetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::SetThreadContext method [.NET Framework debugging]
ms.assetid: 103c8502-81fe-40d7-9c1e-9008d8fb19e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3f98ab65512a380ebd4dc0ecd50e36f94a6d6b5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104156"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="26146-102">Metodo ICLRDataTarget::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="26146-102">ICLRDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="26146-103">Imposta il contesto corrente del thread specificato nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="26146-103">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="26146-104">Questo metodo viene chiamato dai servizi di accesso dati di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="26146-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26146-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="26146-105">Syntax</span></span>  
  
```  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]   
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26146-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="26146-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="26146-107">[in] L'identificatore del sistema operativo di un thread nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="26146-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="26146-108">[in] Le dimensioni del contesto.</span><span class="sxs-lookup"><span data-stu-id="26146-108">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="26146-109">[in] Puntatore a un buffer che contiene il contesto.</span><span class="sxs-lookup"><span data-stu-id="26146-109">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="26146-110">I dati di `context` buffer sarà nel formato Win32 `CONTEXT` struttura.</span><span class="sxs-lookup"><span data-stu-id="26146-110">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="26146-111">Il contesto specifica i dati di registro specifico del processore, pertanto la definizione di Win32 `CONTEXT` struttura dipende dall'architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="26146-111">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="26146-112">Fare riferimento al file di intestazione Winnt. H per la definizione di Win32 `CONTEXT` struttura.</span><span class="sxs-lookup"><span data-stu-id="26146-112">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26146-113">Note</span><span class="sxs-lookup"><span data-stu-id="26146-113">Remarks</span></span>  
 <span data-ttu-id="26146-114">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="26146-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26146-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="26146-115">Requirements</span></span>  
 <span data-ttu-id="26146-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26146-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26146-117">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="26146-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="26146-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26146-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26146-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26146-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26146-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26146-120">See also</span></span>

- [<span data-ttu-id="26146-121">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="26146-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
