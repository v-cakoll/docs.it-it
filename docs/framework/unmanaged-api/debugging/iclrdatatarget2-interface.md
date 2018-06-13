---
title: Interfaccia ICLRDataTarget2
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2
helpviewer_keywords:
- ICLRDataTarget2 interface [.NET Framework debugging]
ms.assetid: 94249397-861b-4294-a538-cf01466a66d3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6fc26694bded2c7df1a53a96e8743f3be73c93eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408504"
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="8af91-102">Interfaccia ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="8af91-102">ICLRDataTarget2 Interface</span></span>
<span data-ttu-id="8af91-103">Una sottoclasse di [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) utilizzato dal livello dei servizi di accesso ai dati per modificare le aree di memoria virtuale nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8af91-103">A subclass of [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8af91-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="8af91-104">Methods</span></span>  
  
|<span data-ttu-id="8af91-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="8af91-105">Method</span></span>|<span data-ttu-id="8af91-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8af91-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8af91-107">Metodo AllocVirtual</span><span class="sxs-lookup"><span data-stu-id="8af91-107">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="8af91-108">Alloca memoria nello spazio degli indirizzi del processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8af91-108">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="8af91-109">Metodo FreeVirtual</span><span class="sxs-lookup"><span data-stu-id="8af91-109">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="8af91-110">Libera la memoria precedentemente allocato nello spazio degli indirizzi del processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8af91-110">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8af91-111">Note</span><span class="sxs-lookup"><span data-stu-id="8af91-111">Remarks</span></span>  
 <span data-ttu-id="8af91-112">Il client API, ovvero il debugger, deve implementare questa interfaccia in modo appropriato per il processo di destinazione specifico.</span><span class="sxs-lookup"><span data-stu-id="8af91-112">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="8af91-113">L'implementazione per un processo reale, ad esempio, è diversa da quella di un dump di memoria.</span><span class="sxs-lookup"><span data-stu-id="8af91-113">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="8af91-114">La destinazione potrebbe non supportare le modifiche delle relative aree di memoria.</span><span class="sxs-lookup"><span data-stu-id="8af91-114">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8af91-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8af91-115">Requirements</span></span>  
 <span data-ttu-id="8af91-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8af91-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8af91-117">**Intestazione:** Clrdata. idl, Clrdata. H</span><span class="sxs-lookup"><span data-stu-id="8af91-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="8af91-118">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="8af91-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8af91-119">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8af91-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8af91-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8af91-120">See Also</span></span>  
 [<span data-ttu-id="8af91-121">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="8af91-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)  
 [<span data-ttu-id="8af91-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="8af91-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
