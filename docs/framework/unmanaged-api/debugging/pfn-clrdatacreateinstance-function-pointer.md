---
title: Puntatore alla funzione PFN_CLRDataCreateInstance
ms.date: 03/30/2017
api_name:
- PFN_CLRDataCreateInstance
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- PFN_CLRDataCreateInstance
helpviewer_keywords:
- PFN_CLRDataCreateInstance function pointer [.NET Framework debugging]
ms.assetid: 5c66ac57-d751-4de5-af9f-26ceb949af8b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ee003d668916baec313c6115cc12826286f6cdd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423676"
---
# <a name="pfnclrdatacreateinstance-function-pointer"></a><span data-ttu-id="52055-102">Puntatore alla funzione PFN_CLRDataCreateInstance</span><span class="sxs-lookup"><span data-stu-id="52055-102">PFN_CLRDataCreateInstance Function Pointer</span></span>
<span data-ttu-id="52055-103">Punta a una funzione che crea un oggetto di interfaccia per l'elemento di destinazione specificato.</span><span class="sxs-lookup"><span data-stu-id="52055-103">Points to a function that creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52055-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="52055-104">Syntax</span></span>  
  
```  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="52055-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="52055-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="52055-106">[in] Identificatore dell'interfaccia per creare un'istanza.</span><span class="sxs-lookup"><span data-stu-id="52055-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="52055-107">[in] Un puntatore a un utente implementato [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) oggetto che rappresenta l'elemento di destinazione per cui creare l'oggetto di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="52055-107">[in] A pointer to a user-implemented [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="52055-108">[out] Un puntatore all'indirizzo dell'oggetto interfaccia restituita.</span><span class="sxs-lookup"><span data-stu-id="52055-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52055-109">Note</span><span class="sxs-lookup"><span data-stu-id="52055-109">Remarks</span></span>  
 <span data-ttu-id="52055-110">Il `ICLRDataTarget` oggetto è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="52055-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="52055-111">L'implementazione varia a seconda del tipo di elemento di destinazione rappresentato.</span><span class="sxs-lookup"><span data-stu-id="52055-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="52055-112">L'elemento di destinazione potrebbe essere un processo, i dump di memoria, computer remoto e così via.</span><span class="sxs-lookup"><span data-stu-id="52055-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52055-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="52055-113">Requirements</span></span>  
 <span data-ttu-id="52055-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52055-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52055-115">**Intestazione:** Clrdata. idl</span><span class="sxs-lookup"><span data-stu-id="52055-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="52055-116">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="52055-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52055-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52055-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52055-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52055-118">See Also</span></span>  
 [<span data-ttu-id="52055-119">Funzioni statiche globali di debug</span><span class="sxs-lookup"><span data-stu-id="52055-119">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
