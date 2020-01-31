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
ms.openlocfilehash: bdc8378a129dd5bb1d9fdcb080c7b5cd53d34091
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789068"
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="4c051-102">Interfaccia ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="4c051-102">ICLRDataTarget2 Interface</span></span>
<span data-ttu-id="4c051-103">Sottoclasse di [ICLRDataTarget](iclrdatatarget-interface.md) utilizzata dal livello servizi di accesso ai dati per modificare le aree della memoria virtuale nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4c051-103">A subclass of [ICLRDataTarget](iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4c051-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="4c051-104">Methods</span></span>  
  
|<span data-ttu-id="4c051-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="4c051-105">Method</span></span>|<span data-ttu-id="4c051-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c051-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4c051-107">Metodo AllocVirtual</span><span class="sxs-lookup"><span data-stu-id="4c051-107">AllocVirtual Method</span></span>](iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="4c051-108">Alloca memoria nello spazio degli indirizzi del processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4c051-108">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="4c051-109">Metodo FreeVirtual</span><span class="sxs-lookup"><span data-stu-id="4c051-109">FreeVirtual Method</span></span>](iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="4c051-110">Libera la memoria allocata in precedenza nello spazio degli indirizzi del processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4c051-110">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c051-111">Note</span><span class="sxs-lookup"><span data-stu-id="4c051-111">Remarks</span></span>  
 <span data-ttu-id="4c051-112">Il client API, ovvero il debugger, deve implementare questa interfaccia in modo appropriato per il processo di destinazione specifico.</span><span class="sxs-lookup"><span data-stu-id="4c051-112">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="4c051-113">L'implementazione per un processo reale, ad esempio, è diversa da quella di un dump di memoria.</span><span class="sxs-lookup"><span data-stu-id="4c051-113">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="4c051-114">La destinazione potrebbe non supportare le modifiche delle relative aree di memoria.</span><span class="sxs-lookup"><span data-stu-id="4c051-114">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c051-115">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="4c051-115">Requirements</span></span>  
 <span data-ttu-id="4c051-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c051-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c051-117">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="4c051-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="4c051-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c051-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c051-119">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c051-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c051-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c051-120">See also</span></span>

- [<span data-ttu-id="4c051-121">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="4c051-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
- [<span data-ttu-id="4c051-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4c051-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
