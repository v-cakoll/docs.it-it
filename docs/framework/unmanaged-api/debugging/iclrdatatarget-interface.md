---
title: Interfaccia ICLRDataTarget
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget
helpviewer_keywords:
- ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: e2f05155-9bef-4e11-b703-7f05890665ca
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 73966ffe89f0e84d5a516f20962472d900332faa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatarget-interface"></a><span data-ttu-id="05383-102">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="05383-102">ICLRDataTarget Interface</span></span>
<span data-ttu-id="05383-103">Fornisce metodi per l'interazione con un elemento di destinazione di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="05383-103">Provides methods for interaction with a target item of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="05383-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="05383-104">Methods</span></span>  
  
|<span data-ttu-id="05383-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="05383-105">Method</span></span>|<span data-ttu-id="05383-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="05383-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="05383-107">Metodo GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="05383-107">GetCurrentThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getcurrentthreadid-method.md)|<span data-ttu-id="05383-108">Ottiene l'identificatore del sistema operativo per il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="05383-108">Gets the operating system identifier for the current thread.</span></span>|  
|[<span data-ttu-id="05383-109">Metodo GetImageBase</span><span class="sxs-lookup"><span data-stu-id="05383-109">GetImageBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getimagebase-method.md)|<span data-ttu-id="05383-110">Ottiene l'indirizzo di memoria di base per l'immagine specificata.</span><span class="sxs-lookup"><span data-stu-id="05383-110">Gets the base memory address for the specified image.</span></span>|  
|[<span data-ttu-id="05383-111">Metodo GetMachineType</span><span class="sxs-lookup"><span data-stu-id="05383-111">GetMachineType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getmachinetype-method.md)|<span data-ttu-id="05383-112">Ottiene un identificatore per il tipo di set di istruzioni che utilizza il processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="05383-112">Gets an identifier for the kind of instruction set that the target process is using.</span></span>|  
|[<span data-ttu-id="05383-113">Metodo GetPointerSize</span><span class="sxs-lookup"><span data-stu-id="05383-113">GetPointerSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getpointersize-method.md)|<span data-ttu-id="05383-114">Ottiene le dimensioni, in byte, di un puntatore alla destinazione corrente.</span><span class="sxs-lookup"><span data-stu-id="05383-114">Gets the size, in bytes, of a pointer to the current target.</span></span>|  
|[<span data-ttu-id="05383-115">Metodo GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="05383-115">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getthreadcontext-method.md)|<span data-ttu-id="05383-116">Ottiene un puntatore al contesto del thread, con l'identificatore specificato.</span><span class="sxs-lookup"><span data-stu-id="05383-116">Gets a pointer to the context of the thread with the specified identifier.</span></span>|  
|[<span data-ttu-id="05383-117">Metodo GetTLSValue</span><span class="sxs-lookup"><span data-stu-id="05383-117">GetTLSValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-gettlsvalue-method.md)|<span data-ttu-id="05383-118">Ottiene un valore nella memoria locale di thread (TLS) in corrispondenza dell'indice specificato per il thread specificato.</span><span class="sxs-lookup"><span data-stu-id="05383-118">Gets a value in thread local storage (TLS) at the specified index for the specified thread.</span></span>|  
|[<span data-ttu-id="05383-119">Metodo ReadVirtual</span><span class="sxs-lookup"><span data-stu-id="05383-119">ReadVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-readvirtual-method.md)|<span data-ttu-id="05383-120">Legge i dati dall'indirizzo di memoria virtuale specificato nel buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="05383-120">Reads data from the specified virtual memory address into the specified buffer.</span></span>|  
|[<span data-ttu-id="05383-121">Metodo Request</span><span class="sxs-lookup"><span data-stu-id="05383-121">Request Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-request-method.md)|<span data-ttu-id="05383-122">Chiamato dai servizi di accesso ai dati di common language runtime (CLR) per richiedere un'operazione, come definito dall'implementazione.</span><span class="sxs-lookup"><span data-stu-id="05383-122">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>|  
|[<span data-ttu-id="05383-123">Metodo SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="05383-123">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-setthreadcontext-method.md)|<span data-ttu-id="05383-124">Imposta il contesto corrente del thread specificato nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="05383-124">Sets the current context of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="05383-125">Metodo SetTLSValue</span><span class="sxs-lookup"><span data-stu-id="05383-125">SetTLSValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-settlsvalue-method.md)|<span data-ttu-id="05383-126">Imposta un valore nell'archiviazione locale di thread (TLS) del thread nel processo di destinazione specificato.</span><span class="sxs-lookup"><span data-stu-id="05383-126">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="05383-127">Metodo WriteVirtual</span><span class="sxs-lookup"><span data-stu-id="05383-127">WriteVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-writevirtual-method.md)|<span data-ttu-id="05383-128">Scrive dati dal buffer specificato per l'indirizzo di memoria virtuale specificato.</span><span class="sxs-lookup"><span data-stu-id="05383-128">Writes data from the specified buffer to the specified virtual memory address.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05383-129">Note</span><span class="sxs-lookup"><span data-stu-id="05383-129">Remarks</span></span>  
 <span data-ttu-id="05383-130">Il client di API (ovvero, il debugger) deve implementare questa interfaccia in modo appropriato per l'elemento di destinazione specifico.</span><span class="sxs-lookup"><span data-stu-id="05383-130">The API client (that is, the debugger) must implement this interface as appropriate for the particular target item.</span></span> <span data-ttu-id="05383-131">L'implementazione per un processo reale, ad esempio, è diversa da quella di un dump di memoria.</span><span class="sxs-lookup"><span data-stu-id="05383-131">For example, a live process would have an implementation different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05383-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="05383-132">Requirements</span></span>  
 <span data-ttu-id="05383-133">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05383-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05383-134">**Intestazione:** ClrData.idl, Clrdata. H</span><span class="sxs-lookup"><span data-stu-id="05383-134">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="05383-135">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05383-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05383-136">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05383-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05383-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05383-137">See Also</span></span>  
 [<span data-ttu-id="05383-138">Interfaccia ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="05383-138">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [<span data-ttu-id="05383-139">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="05383-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
