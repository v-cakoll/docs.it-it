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
ms.openlocfilehash: d76a907434b12b85aaedeef169390ec6f0df724a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179121"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="3eb16-102">Metodo ICLRDataTarget::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="3eb16-102">ICLRDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="3eb16-103">Imposta il contesto corrente del thread specificato nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3eb16-103">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="3eb16-104">Questo metodo viene chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="3eb16-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eb16-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3eb16-105">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3eb16-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="3eb16-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="3eb16-107">[in] Identificatore del sistema operativo di un thread nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3eb16-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="3eb16-108">[in] Dimensione del contesto.</span><span class="sxs-lookup"><span data-stu-id="3eb16-108">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="3eb16-109">[in] Puntatore a un buffer contenente il contesto.</span><span class="sxs-lookup"><span data-stu-id="3eb16-109">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="3eb16-110">I dati `context` nel buffer saranno nel formato della `CONTEXT` struttura Win32.</span><span class="sxs-lookup"><span data-stu-id="3eb16-110">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="3eb16-111">Il contesto specifica i dati del registro specifici `CONTEXT` del processore, pertanto la definizione della struttura Win32 dipende dall'architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="3eb16-111">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="3eb16-112">Fare riferimento al file di intestazione WinNT.h `CONTEXT` per la definizione della struttura Win32.</span><span class="sxs-lookup"><span data-stu-id="3eb16-112">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3eb16-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3eb16-113">Remarks</span></span>  
 <span data-ttu-id="3eb16-114">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="3eb16-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3eb16-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3eb16-115">Requirements</span></span>  
 <span data-ttu-id="3eb16-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3eb16-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3eb16-117">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="3eb16-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="3eb16-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3eb16-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3eb16-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3eb16-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eb16-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3eb16-120">See also</span></span>

- [<span data-ttu-id="3eb16-121">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="3eb16-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
