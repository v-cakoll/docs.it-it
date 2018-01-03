---
title: Metodo ICLRDataTarget::SetThreadContext
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.SetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::SetThreadContext
helpviewer_keywords:
- SetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::SetThreadContext method [.NET Framework debugging]
ms.assetid: 103c8502-81fe-40d7-9c1e-9008d8fb19e1
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 02b77bbb721a44ff24734499011402f2b9165ef4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="76565-102">Metodo ICLRDataTarget::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="76565-102">ICLRDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="76565-103">Imposta il contesto corrente del thread specificato nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="76565-103">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="76565-104">Questo metodo viene chiamato da servizi di accesso dati di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="76565-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76565-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="76565-105">Syntax</span></span>  
  
```  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]   
         BYTE               *context  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="76565-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="76565-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="76565-107">[in] Identificatore del sistema operativo di un thread nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="76565-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="76565-108">[in] Le dimensioni del contesto.</span><span class="sxs-lookup"><span data-stu-id="76565-108">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="76565-109">[in] Puntatore a un buffer contenente il contesto.</span><span class="sxs-lookup"><span data-stu-id="76565-109">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="76565-110">I dati di `context` buffer sarà nel formato Win32 `CONTEXT` struttura.</span><span class="sxs-lookup"><span data-stu-id="76565-110">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="76565-111">Il contesto specifica i dati di registro specifici, la definizione di Win32 `CONTEXT` struttura dipende dall'architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="76565-111">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="76565-112">Fare riferimento al file di intestazione Winnt. H per la definizione dell'oggetto Win32 `CONTEXT` struttura.</span><span class="sxs-lookup"><span data-stu-id="76565-112">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76565-113">Note</span><span class="sxs-lookup"><span data-stu-id="76565-113">Remarks</span></span>  
 <span data-ttu-id="76565-114">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="76565-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76565-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="76565-115">Requirements</span></span>  
 <span data-ttu-id="76565-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76565-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76565-117">**Intestazione:** ClrData.idl, Clrdata. H</span><span class="sxs-lookup"><span data-stu-id="76565-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="76565-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76565-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76565-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76565-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76565-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76565-120">See Also</span></span>  
 [<span data-ttu-id="76565-121">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="76565-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
