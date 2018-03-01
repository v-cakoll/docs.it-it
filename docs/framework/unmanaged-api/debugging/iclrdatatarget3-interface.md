---
title: Interfaccia ICLRDataTarget3
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
- ICLRDataTarget3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d2711bdf-64b3-404c-a0c3-01ba4907f703
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 64ecb4ca4dfd829bb140c3067085c55a7b86c919
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatarget3-interface"></a><span data-ttu-id="57523-102">Interfaccia ICLRDataTarget3</span><span class="sxs-lookup"><span data-stu-id="57523-102">ICLRDataTarget3 Interface</span></span>
<span data-ttu-id="57523-103">Una sottoclasse di [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) che consente di accedere alle informazioni sulle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="57523-103">A subclass of [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="57523-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="57523-104">Methods</span></span>  
  
|<span data-ttu-id="57523-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="57523-105">Method</span></span>|<span data-ttu-id="57523-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57523-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="57523-107">Metodo GetExceptionRecord</span><span class="sxs-lookup"><span data-stu-id="57523-107">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)|<span data-ttu-id="57523-108">Chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR) per recuperare il record di eccezione associato al processo destinazione.</span><span class="sxs-lookup"><span data-stu-id="57523-108">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span>|  
|[<span data-ttu-id="57523-109">Metodo GetExceptionContextRecord</span><span class="sxs-lookup"><span data-stu-id="57523-109">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)|<span data-ttu-id="57523-110">Chiamato dai servizi di accesso ai dati CLR per recuperare il record di contesto associato al processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="57523-110">Called by the CLR data access services to retrieve the context record associated with the target process.</span></span>|  
|[<span data-ttu-id="57523-111">Metodo GetExceptionThreadID</span><span class="sxs-lookup"><span data-stu-id="57523-111">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)|<span data-ttu-id="57523-112">Chiamato dai servizi di accesso ai dati CLR per ottenere l'ID del thread che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="57523-112">Called by the CLR data access services to get the ID of the thread that threw the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57523-113">Note</span><span class="sxs-lookup"><span data-stu-id="57523-113">Remarks</span></span>  
 <span data-ttu-id="57523-114">Il client API, ovvero il debugger, deve implementare questa interfaccia in modo appropriato per il processo di destinazione specifico.</span><span class="sxs-lookup"><span data-stu-id="57523-114">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="57523-115">L'implementazione per un processo reale, ad esempio, è diversa da quella di un dump di memoria.</span><span class="sxs-lookup"><span data-stu-id="57523-115">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="57523-116">La destinazione potrebbe non supportare le modifiche delle relative aree di memoria.</span><span class="sxs-lookup"><span data-stu-id="57523-116">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57523-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="57523-117">Requirements</span></span>  
 <span data-ttu-id="57523-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57523-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57523-119">**Intestazione:** ClrData.idl, Clrdata. H</span><span class="sxs-lookup"><span data-stu-id="57523-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="57523-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57523-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57523-121">**Versioni di .NET framework:**[!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57523-121">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57523-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57523-122">See Also</span></span>  
 [<span data-ttu-id="57523-123">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="57523-123">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)  
 [<span data-ttu-id="57523-124">Interfaccia ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="57523-124">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [<span data-ttu-id="57523-125">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="57523-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
