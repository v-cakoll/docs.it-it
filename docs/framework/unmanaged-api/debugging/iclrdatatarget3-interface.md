---
title: Interfaccia ICLRDataTarget3
ms.date: 03/30/2017
api_name:
- ICLRDataTarget3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d2711bdf-64b3-404c-a0c3-01ba4907f703
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: df113a2839b0f2651e15f4029d86cc5efc171c63
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111813"
---
# <a name="iclrdatatarget3-interface"></a><span data-ttu-id="7a723-102">Interfaccia ICLRDataTarget3</span><span class="sxs-lookup"><span data-stu-id="7a723-102">ICLRDataTarget3 Interface</span></span>
<span data-ttu-id="7a723-103">Una sottoclasse [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) che fornisce accesso alle informazioni sull'eccezione.</span><span class="sxs-lookup"><span data-stu-id="7a723-103">A subclass of [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7a723-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="7a723-104">Methods</span></span>  
  
|<span data-ttu-id="7a723-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="7a723-105">Method</span></span>|<span data-ttu-id="7a723-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a723-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7a723-107">Metodo GetExceptionRecord</span><span class="sxs-lookup"><span data-stu-id="7a723-107">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)|<span data-ttu-id="7a723-108">Chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR) per recuperare il record di eccezione associato al processo destinazione.</span><span class="sxs-lookup"><span data-stu-id="7a723-108">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span>|  
|[<span data-ttu-id="7a723-109">Metodo GetExceptionContextRecord</span><span class="sxs-lookup"><span data-stu-id="7a723-109">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)|<span data-ttu-id="7a723-110">Chiamato dai servizi di accesso ai dati CLR per recuperare il record di contesto associato al processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7a723-110">Called by the CLR data access services to retrieve the context record associated with the target process.</span></span>|  
|[<span data-ttu-id="7a723-111">Metodo GetExceptionThreadID</span><span class="sxs-lookup"><span data-stu-id="7a723-111">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)|<span data-ttu-id="7a723-112">Chiamato dai servizi di accesso ai dati CLR per ottenere l'ID del thread che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="7a723-112">Called by the CLR data access services to get the ID of the thread that threw the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a723-113">Note</span><span class="sxs-lookup"><span data-stu-id="7a723-113">Remarks</span></span>  
 <span data-ttu-id="7a723-114">Il client API, ovvero il debugger, deve implementare questa interfaccia in modo appropriato per il processo di destinazione specifico.</span><span class="sxs-lookup"><span data-stu-id="7a723-114">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="7a723-115">L'implementazione per un processo reale, ad esempio, è diversa da quella di un dump di memoria.</span><span class="sxs-lookup"><span data-stu-id="7a723-115">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="7a723-116">La destinazione potrebbe non supportare le modifiche delle relative aree di memoria.</span><span class="sxs-lookup"><span data-stu-id="7a723-116">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a723-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7a723-117">Requirements</span></span>  
 <span data-ttu-id="7a723-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a723-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a723-119">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="7a723-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="7a723-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a723-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a723-121">**Versioni di .NET Framework:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7a723-121">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a723-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a723-122">See also</span></span>

- [<span data-ttu-id="7a723-123">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="7a723-123">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
- [<span data-ttu-id="7a723-124">Interfaccia ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="7a723-124">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="7a723-125">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="7a723-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
