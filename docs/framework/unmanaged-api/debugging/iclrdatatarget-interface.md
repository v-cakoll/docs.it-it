---
title: Interfaccia ICLRDataTarget
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ed3cb62b56e80a7fe4ea54b43ac9f4a28b8d102
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59100249"
---
# <a name="iclrdatatarget-interface"></a><span data-ttu-id="91704-102">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="91704-102">ICLRDataTarget Interface</span></span>
<span data-ttu-id="91704-103">Fornisce metodi per l'interazione con un elemento di destinazione di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="91704-103">Provides methods for interaction with a target item of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="91704-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="91704-104">Methods</span></span>  
  
|<span data-ttu-id="91704-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="91704-105">Method</span></span>|<span data-ttu-id="91704-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91704-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="91704-107">Metodo GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="91704-107">GetCurrentThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getcurrentthreadid-method.md)|<span data-ttu-id="91704-108">Ottiene l'identificatore del sistema operativo per il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="91704-108">Gets the operating system identifier for the current thread.</span></span>|  
|[<span data-ttu-id="91704-109">Metodo GetImageBase</span><span class="sxs-lookup"><span data-stu-id="91704-109">GetImageBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getimagebase-method.md)|<span data-ttu-id="91704-110">Ottiene l'indirizzo di base di memoria per l'immagine specificata.</span><span class="sxs-lookup"><span data-stu-id="91704-110">Gets the base memory address for the specified image.</span></span>|  
|[<span data-ttu-id="91704-111">Metodo GetMachineType</span><span class="sxs-lookup"><span data-stu-id="91704-111">GetMachineType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getmachinetype-method.md)|<span data-ttu-id="91704-112">Ottiene un identificatore per il tipo di set di istruzioni che utilizza il processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="91704-112">Gets an identifier for the kind of instruction set that the target process is using.</span></span>|  
|[<span data-ttu-id="91704-113">Metodo GetPointerSize</span><span class="sxs-lookup"><span data-stu-id="91704-113">GetPointerSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getpointersize-method.md)|<span data-ttu-id="91704-114">Ottiene la dimensione, espressa in byte, di un puntatore alla destinazione corrente.</span><span class="sxs-lookup"><span data-stu-id="91704-114">Gets the size, in bytes, of a pointer to the current target.</span></span>|  
|[<span data-ttu-id="91704-115">Metodo GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="91704-115">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getthreadcontext-method.md)|<span data-ttu-id="91704-116">Ottiene un puntatore al contesto del thread con l'identificatore specificato.</span><span class="sxs-lookup"><span data-stu-id="91704-116">Gets a pointer to the context of the thread with the specified identifier.</span></span>|  
|[<span data-ttu-id="91704-117">Metodo GetTLSValue</span><span class="sxs-lookup"><span data-stu-id="91704-117">GetTLSValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-gettlsvalue-method.md)|<span data-ttu-id="91704-118">Ottiene un valore nell'archiviazione thread-local (TLS) in corrispondenza dell'indice specificato per il thread specificato.</span><span class="sxs-lookup"><span data-stu-id="91704-118">Gets a value in thread local storage (TLS) at the specified index for the specified thread.</span></span>|  
|[<span data-ttu-id="91704-119">Metodo ReadVirtual</span><span class="sxs-lookup"><span data-stu-id="91704-119">ReadVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-readvirtual-method.md)|<span data-ttu-id="91704-120">Legge i dati dall'indirizzo di memoria virtuale specificato nel buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="91704-120">Reads data from the specified virtual memory address into the specified buffer.</span></span>|  
|[<span data-ttu-id="91704-121">Metodo Request</span><span class="sxs-lookup"><span data-stu-id="91704-121">Request Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-request-method.md)|<span data-ttu-id="91704-122">Chiamato dai servizi di accesso ai dati di common language runtime (CLR) per richiedere un'operazione, come definito dall'implementazione.</span><span class="sxs-lookup"><span data-stu-id="91704-122">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>|  
|[<span data-ttu-id="91704-123">Metodo SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="91704-123">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-setthreadcontext-method.md)|<span data-ttu-id="91704-124">Imposta il contesto corrente del thread specificato nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="91704-124">Sets the current context of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="91704-125">Metodo SetTLSValue</span><span class="sxs-lookup"><span data-stu-id="91704-125">SetTLSValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-settlsvalue-method.md)|<span data-ttu-id="91704-126">Imposta un valore nell'archiviazione thread-local (TLS) del thread nel processo di destinazione specificato.</span><span class="sxs-lookup"><span data-stu-id="91704-126">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="91704-127">Metodo WriteVirtual</span><span class="sxs-lookup"><span data-stu-id="91704-127">WriteVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-writevirtual-method.md)|<span data-ttu-id="91704-128">Scrive i dati dal buffer specificato per l'indirizzo di memoria virtuale specificato.</span><span class="sxs-lookup"><span data-stu-id="91704-128">Writes data from the specified buffer to the specified virtual memory address.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91704-129">Note</span><span class="sxs-lookup"><span data-stu-id="91704-129">Remarks</span></span>  
 <span data-ttu-id="91704-130">Il client per le API (vale a dire, il debugger) deve implementare questa interfaccia in modo appropriato per l'elemento di destinazione specifico.</span><span class="sxs-lookup"><span data-stu-id="91704-130">The API client (that is, the debugger) must implement this interface as appropriate for the particular target item.</span></span> <span data-ttu-id="91704-131">L'implementazione per un processo reale, ad esempio, è diversa da quella di un dump di memoria.</span><span class="sxs-lookup"><span data-stu-id="91704-131">For example, a live process would have an implementation different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91704-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="91704-132">Requirements</span></span>  
 <span data-ttu-id="91704-133">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91704-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91704-134">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="91704-134">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="91704-135">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91704-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91704-136">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91704-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91704-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91704-137">See also</span></span>

- [<span data-ttu-id="91704-138">Interfaccia ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="91704-138">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="91704-139">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="91704-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
