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
ms.openlocfilehash: 30806394a8895084068acaec6f7d03c6b67bb14b
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860571"
---
# <a name="iclrdatatarget-interface"></a><span data-ttu-id="704d8-102">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="704d8-102">ICLRDataTarget Interface</span></span>
<span data-ttu-id="704d8-103">Fornisce metodi per l'interazione con un elemento di destinazione del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="704d8-103">Provides methods for interaction with a target item of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="704d8-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="704d8-104">Methods</span></span>  
  
|<span data-ttu-id="704d8-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="704d8-105">Method</span></span>|<span data-ttu-id="704d8-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="704d8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="704d8-107">Metodo GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="704d8-107">GetCurrentThreadID Method</span></span>](iclrdatatarget-getcurrentthreadid-method.md)|<span data-ttu-id="704d8-108">Ottiene l'identificatore del sistema operativo per il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="704d8-108">Gets the operating system identifier for the current thread.</span></span>|  
|[<span data-ttu-id="704d8-109">Metodo GetImageBase</span><span class="sxs-lookup"><span data-stu-id="704d8-109">GetImageBase Method</span></span>](iclrdatatarget-getimagebase-method.md)|<span data-ttu-id="704d8-110">Ottiene l'indirizzo di memoria di base per l'immagine specificata.</span><span class="sxs-lookup"><span data-stu-id="704d8-110">Gets the base memory address for the specified image.</span></span>|  
|[<span data-ttu-id="704d8-111">Metodo GetMachineType</span><span class="sxs-lookup"><span data-stu-id="704d8-111">GetMachineType Method</span></span>](iclrdatatarget-getmachinetype-method.md)|<span data-ttu-id="704d8-112">Ottiene un identificatore per il tipo di set di istruzioni utilizzato dal processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="704d8-112">Gets an identifier for the kind of instruction set that the target process is using.</span></span>|  
|[<span data-ttu-id="704d8-113">Metodo GetPointerSize</span><span class="sxs-lookup"><span data-stu-id="704d8-113">GetPointerSize Method</span></span>](iclrdatatarget-getpointersize-method.md)|<span data-ttu-id="704d8-114">Ottiene la dimensione, in byte, di un puntatore alla destinazione corrente.</span><span class="sxs-lookup"><span data-stu-id="704d8-114">Gets the size, in bytes, of a pointer to the current target.</span></span>|  
|[<span data-ttu-id="704d8-115">Metodo GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="704d8-115">GetThreadContext Method</span></span>](iclrdatatarget-getthreadcontext-method.md)|<span data-ttu-id="704d8-116">Ottiene un puntatore al contesto del thread con l'identificatore specificato.</span><span class="sxs-lookup"><span data-stu-id="704d8-116">Gets a pointer to the context of the thread with the specified identifier.</span></span>|  
|[<span data-ttu-id="704d8-117">Metodo GetTLSValue</span><span class="sxs-lookup"><span data-stu-id="704d8-117">GetTLSValue Method</span></span>](iclrdatatarget-gettlsvalue-method.md)|<span data-ttu-id="704d8-118">Ottiene un valore nella risorsa di archiviazione thread-local (TLS) in corrispondenza dell'indice specificato per il thread specificato.</span><span class="sxs-lookup"><span data-stu-id="704d8-118">Gets a value in thread local storage (TLS) at the specified index for the specified thread.</span></span>|  
|[<span data-ttu-id="704d8-119">Metodo ReadVirtual</span><span class="sxs-lookup"><span data-stu-id="704d8-119">ReadVirtual Method</span></span>](iclrdatatarget-readvirtual-method.md)|<span data-ttu-id="704d8-120">Legge i dati dall'indirizzo di memoria virtuale specificato nel buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="704d8-120">Reads data from the specified virtual memory address into the specified buffer.</span></span>|  
|[<span data-ttu-id="704d8-121">Metodo Request</span><span class="sxs-lookup"><span data-stu-id="704d8-121">Request Method</span></span>](iclrdatatarget-request-method.md)|<span data-ttu-id="704d8-122">Chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR) per richiedere un'operazione, come definito dall'implementazione di.</span><span class="sxs-lookup"><span data-stu-id="704d8-122">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>|  
|[<span data-ttu-id="704d8-123">Metodo SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="704d8-123">SetThreadContext Method</span></span>](iclrdatatarget-setthreadcontext-method.md)|<span data-ttu-id="704d8-124">Imposta il contesto corrente del thread specificato nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="704d8-124">Sets the current context of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="704d8-125">Metodo SetTLSValue</span><span class="sxs-lookup"><span data-stu-id="704d8-125">SetTLSValue Method</span></span>](iclrdatatarget-settlsvalue-method.md)|<span data-ttu-id="704d8-126">Imposta un valore nell'archiviazione locale di thread (TLS) del thread specificato nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="704d8-126">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="704d8-127">Metodo WriteVirtual</span><span class="sxs-lookup"><span data-stu-id="704d8-127">WriteVirtual Method</span></span>](iclrdatatarget-writevirtual-method.md)|<span data-ttu-id="704d8-128">Scrive i dati dal buffer specificato nell'indirizzo di memoria virtuale specificato.</span><span class="sxs-lookup"><span data-stu-id="704d8-128">Writes data from the specified buffer to the specified virtual memory address.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="704d8-129">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="704d8-129">Remarks</span></span>  
 <span data-ttu-id="704d8-130">Il client API (ovvero il debugger) deve implementare questa interfaccia in modo appropriato per l'elemento di destinazione specifico.</span><span class="sxs-lookup"><span data-stu-id="704d8-130">The API client (that is, the debugger) must implement this interface as appropriate for the particular target item.</span></span> <span data-ttu-id="704d8-131">L'implementazione per un processo reale, ad esempio, è diversa da quella di un dump di memoria.</span><span class="sxs-lookup"><span data-stu-id="704d8-131">For example, a live process would have an implementation different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="704d8-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="704d8-132">Requirements</span></span>  
 <span data-ttu-id="704d8-133">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="704d8-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="704d8-134">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="704d8-134">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="704d8-135">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="704d8-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="704d8-136">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="704d8-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="704d8-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="704d8-137">See also</span></span>

- [<span data-ttu-id="704d8-138">Interfaccia ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="704d8-138">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="704d8-139">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="704d8-139">Debugging Interfaces</span></span>](debugging-interfaces.md)
