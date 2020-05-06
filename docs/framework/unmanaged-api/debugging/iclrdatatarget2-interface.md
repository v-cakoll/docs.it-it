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
ms.openlocfilehash: 6b2700b2f12e312f06640a06e5ec82fbc58f2ca9
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860458"
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="c7ee2-102">Interfaccia ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="c7ee2-102">ICLRDataTarget2 Interface</span></span>
<span data-ttu-id="c7ee2-103">Sottoclasse di [ICLRDataTarget](iclrdatatarget-interface.md) utilizzata dal livello servizi di accesso ai dati per modificare le aree della memoria virtuale nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c7ee2-103">A subclass of [ICLRDataTarget](iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c7ee2-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c7ee2-104">Methods</span></span>  
  
|<span data-ttu-id="c7ee2-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c7ee2-105">Method</span></span>|<span data-ttu-id="c7ee2-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c7ee2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c7ee2-107">Metodo AllocVirtual</span><span class="sxs-lookup"><span data-stu-id="c7ee2-107">AllocVirtual Method</span></span>](iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="c7ee2-108">Alloca memoria nello spazio degli indirizzi del processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c7ee2-108">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="c7ee2-109">Metodo FreeVirtual</span><span class="sxs-lookup"><span data-stu-id="c7ee2-109">FreeVirtual Method</span></span>](iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="c7ee2-110">Libera la memoria allocata in precedenza nello spazio degli indirizzi del processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c7ee2-110">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7ee2-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c7ee2-111">Remarks</span></span>  
 <span data-ttu-id="c7ee2-112">Il client API, ovvero il debugger, deve implementare questa interfaccia in modo appropriato per il processo di destinazione specifico.</span><span class="sxs-lookup"><span data-stu-id="c7ee2-112">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="c7ee2-113">L'implementazione per un processo reale, ad esempio, è diversa da quella di un dump di memoria.</span><span class="sxs-lookup"><span data-stu-id="c7ee2-113">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="c7ee2-114">La destinazione potrebbe non supportare le modifiche delle relative aree di memoria.</span><span class="sxs-lookup"><span data-stu-id="c7ee2-114">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7ee2-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c7ee2-115">Requirements</span></span>  
 <span data-ttu-id="c7ee2-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7ee2-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7ee2-117">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="c7ee2-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c7ee2-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7ee2-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7ee2-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7ee2-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7ee2-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7ee2-120">See also</span></span>

- [<span data-ttu-id="c7ee2-121">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="c7ee2-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
- [<span data-ttu-id="c7ee2-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c7ee2-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
