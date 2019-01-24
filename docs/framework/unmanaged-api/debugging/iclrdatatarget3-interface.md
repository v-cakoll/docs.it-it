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
ms.openlocfilehash: 974abb123c4c11f6bb512431cea5cc6460a5c55a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654740"
---
# <a name="iclrdatatarget3-interface"></a><span data-ttu-id="5406e-102">Interfaccia ICLRDataTarget3</span><span class="sxs-lookup"><span data-stu-id="5406e-102">ICLRDataTarget3 Interface</span></span>
<span data-ttu-id="5406e-103">Una sottoclasse [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) che fornisce accesso alle informazioni sull'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5406e-103">A subclass of [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5406e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="5406e-104">Methods</span></span>  
  
|<span data-ttu-id="5406e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="5406e-105">Method</span></span>|<span data-ttu-id="5406e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5406e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5406e-107">Metodo GetExceptionRecord</span><span class="sxs-lookup"><span data-stu-id="5406e-107">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)|<span data-ttu-id="5406e-108">Chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR) per recuperare il record di eccezione associato al processo destinazione.</span><span class="sxs-lookup"><span data-stu-id="5406e-108">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span>|  
|[<span data-ttu-id="5406e-109">Metodo GetExceptionContextRecord</span><span class="sxs-lookup"><span data-stu-id="5406e-109">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)|<span data-ttu-id="5406e-110">Chiamato dai servizi di accesso ai dati CLR per recuperare il record di contesto associato al processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5406e-110">Called by the CLR data access services to retrieve the context record associated with the target process.</span></span>|  
|[<span data-ttu-id="5406e-111">Metodo GetExceptionThreadID</span><span class="sxs-lookup"><span data-stu-id="5406e-111">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)|<span data-ttu-id="5406e-112">Chiamato dai servizi di accesso ai dati CLR per ottenere l'ID del thread che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5406e-112">Called by the CLR data access services to get the ID of the thread that threw the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5406e-113">Note</span><span class="sxs-lookup"><span data-stu-id="5406e-113">Remarks</span></span>  
 <span data-ttu-id="5406e-114">Il client API, ovvero il debugger, deve implementare questa interfaccia in modo appropriato per il processo di destinazione specifico.</span><span class="sxs-lookup"><span data-stu-id="5406e-114">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="5406e-115">L'implementazione per un processo reale, ad esempio, è diversa da quella di un dump di memoria.</span><span class="sxs-lookup"><span data-stu-id="5406e-115">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="5406e-116">La destinazione potrebbe non supportare le modifiche delle relative aree di memoria.</span><span class="sxs-lookup"><span data-stu-id="5406e-116">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5406e-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5406e-117">Requirements</span></span>  
 <span data-ttu-id="5406e-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5406e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5406e-119">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="5406e-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="5406e-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5406e-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5406e-121">**Versioni di .NET Framework:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5406e-121">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5406e-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5406e-122">See also</span></span>
- [<span data-ttu-id="5406e-123">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="5406e-123">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
- [<span data-ttu-id="5406e-124">Interfaccia ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="5406e-124">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="5406e-125">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="5406e-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
