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
ms.openlocfilehash: a6591f7d7b632bcdbdabb1633f7431d79da7ff6e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73111820"
---
# <a name="iclrdatatarget3-interface"></a><span data-ttu-id="18799-102">Interfaccia ICLRDataTarget3</span><span class="sxs-lookup"><span data-stu-id="18799-102">ICLRDataTarget3 Interface</span></span>
<span data-ttu-id="18799-103">Sottoclasse di [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) che fornisce l'accesso alle informazioni sull'eccezione.</span><span class="sxs-lookup"><span data-stu-id="18799-103">A subclass of [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="18799-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="18799-104">Methods</span></span>  
  
|<span data-ttu-id="18799-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="18799-105">Method</span></span>|<span data-ttu-id="18799-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18799-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="18799-107">Metodo GetExceptionRecord</span><span class="sxs-lookup"><span data-stu-id="18799-107">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)|<span data-ttu-id="18799-108">Chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR) per recuperare il record di eccezione associato al processo destinazione.</span><span class="sxs-lookup"><span data-stu-id="18799-108">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span>|  
|[<span data-ttu-id="18799-109">Metodo GetExceptionContextRecord</span><span class="sxs-lookup"><span data-stu-id="18799-109">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)|<span data-ttu-id="18799-110">Chiamato dai servizi di accesso ai dati CLR per recuperare il record di contesto associato al processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="18799-110">Called by the CLR data access services to retrieve the context record associated with the target process.</span></span>|  
|[<span data-ttu-id="18799-111">Metodo GetExceptionThreadID</span><span class="sxs-lookup"><span data-stu-id="18799-111">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)|<span data-ttu-id="18799-112">Chiamato dai servizi di accesso ai dati CLR per ottenere l'ID del thread che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="18799-112">Called by the CLR data access services to get the ID of the thread that threw the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18799-113">Note</span><span class="sxs-lookup"><span data-stu-id="18799-113">Remarks</span></span>  
 <span data-ttu-id="18799-114">Il client API, ovvero il debugger, deve implementare questa interfaccia in modo appropriato per il processo di destinazione specifico.</span><span class="sxs-lookup"><span data-stu-id="18799-114">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="18799-115">L'implementazione per un processo reale, ad esempio, è diversa da quella di un dump di memoria.</span><span class="sxs-lookup"><span data-stu-id="18799-115">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="18799-116">La destinazione potrebbe non supportare le modifiche delle relative aree di memoria.</span><span class="sxs-lookup"><span data-stu-id="18799-116">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18799-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="18799-117">Requirements</span></span>  
 <span data-ttu-id="18799-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18799-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18799-119">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="18799-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="18799-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18799-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18799-121">**Versioni di .NET Framework:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="18799-121">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18799-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18799-122">See also</span></span>

- [<span data-ttu-id="18799-123">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="18799-123">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
- [<span data-ttu-id="18799-124">Interfaccia ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="18799-124">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="18799-125">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="18799-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
