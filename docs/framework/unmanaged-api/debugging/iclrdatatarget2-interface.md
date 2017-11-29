---
title: Interfaccia ICLRDataTarget2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget2
helpviewer_keywords: ICLRDataTarget2 interface [.NET Framework debugging]
ms.assetid: 94249397-861b-4294-a538-cf01466a66d3
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d1780df0a4659d232a27faf4fdc2f6c9b13db98a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="2e2c5-102">Interfaccia ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="2e2c5-102">ICLRDataTarget2 Interface</span></span>
<span data-ttu-id="2e2c5-103">Una sottoclasse di [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) utilizzato dal livello dei servizi di accesso ai dati per modificare le aree di memoria virtuale nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2e2c5-103">A subclass of [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2e2c5-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="2e2c5-104">Methods</span></span>  
  
|<span data-ttu-id="2e2c5-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="2e2c5-105">Method</span></span>|<span data-ttu-id="2e2c5-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e2c5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2e2c5-107">AllocVirtual (metodo)</span><span class="sxs-lookup"><span data-stu-id="2e2c5-107">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="2e2c5-108">Alloca memoria nello spazio degli indirizzi del processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2e2c5-108">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="2e2c5-109">FreeVirtual (metodo)</span><span class="sxs-lookup"><span data-stu-id="2e2c5-109">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="2e2c5-110">Libera la memoria precedentemente allocato nello spazio degli indirizzi del processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2e2c5-110">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e2c5-111">Note</span><span class="sxs-lookup"><span data-stu-id="2e2c5-111">Remarks</span></span>  
 <span data-ttu-id="2e2c5-112">Il client API, ovvero il debugger, deve implementare questa interfaccia in modo appropriato per il processo di destinazione specifico.</span><span class="sxs-lookup"><span data-stu-id="2e2c5-112">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="2e2c5-113">L'implementazione per un processo reale, ad esempio, è diversa da quella di un dump di memoria.</span><span class="sxs-lookup"><span data-stu-id="2e2c5-113">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="2e2c5-114">La destinazione potrebbe non supportare le modifiche delle relative aree di memoria.</span><span class="sxs-lookup"><span data-stu-id="2e2c5-114">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e2c5-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2e2c5-115">Requirements</span></span>  
 <span data-ttu-id="2e2c5-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e2c5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e2c5-117">**Intestazione:** ClrData.idl, Clrdata. H</span><span class="sxs-lookup"><span data-stu-id="2e2c5-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="2e2c5-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e2c5-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e2c5-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e2c5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e2c5-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e2c5-120">See Also</span></span>  
 [<span data-ttu-id="2e2c5-121">ICLRDataTarget (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="2e2c5-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)  
 [<span data-ttu-id="2e2c5-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="2e2c5-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
