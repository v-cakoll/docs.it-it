---
title: Funzione CLRDataCreateInstance
ms.date: 03/30/2017
api_name:
- CLRDataCreateInstance
api_location:
- mscordbi.dll
- mscordacwks.dll
api_type:
- COM
f1_keywords:
- CLRDataCreateInstance
helpviewer_keywords:
- CLRDataCreateInstance function [.NET Framework debugging]
ms.assetid: 440bad90-5a88-45e7-9157-4596801d8d19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a839eb2edd36dc726c819a819fd4d427fbaea40
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740999"
---
# <a name="clrdatacreateinstance-function"></a><span data-ttu-id="451c7-102">Funzione CLRDataCreateInstance</span><span class="sxs-lookup"><span data-stu-id="451c7-102">CLRDataCreateInstance Function</span></span>
<span data-ttu-id="451c7-103">Crea un oggetto di interfaccia per l'elemento di destinazione specificato.</span><span class="sxs-lookup"><span data-stu-id="451c7-103">Creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="451c7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="451c7-104">Syntax</span></span>  
  
```cpp  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,   
    [in]  ICLRDataTarget  *target,   
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="451c7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="451c7-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="451c7-106">[in] L'identificatore dell'interfaccia da cui creare istanze.</span><span class="sxs-lookup"><span data-stu-id="451c7-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="451c7-107">[in] Un puntatore a un utente implementate [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) oggetto che rappresenta l'elemento di destinazione per cui creare l'oggetto di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="451c7-107">[in] A pointer to a user-implemented [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="451c7-108">[out] Un puntatore all'indirizzo dell'oggetto interfaccia restituita.</span><span class="sxs-lookup"><span data-stu-id="451c7-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="451c7-109">Note</span><span class="sxs-lookup"><span data-stu-id="451c7-109">Remarks</span></span>  
 <span data-ttu-id="451c7-110">Il `ICLRDataTarget` oggetto viene implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="451c7-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="451c7-111">L'implementazione dipende dal tipo di elemento di destinazione rappresentato.</span><span class="sxs-lookup"><span data-stu-id="451c7-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="451c7-112">L'elemento di destinazione può essere un processo, dump della memoria, computer remoto e così via.</span><span class="sxs-lookup"><span data-stu-id="451c7-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="451c7-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="451c7-113">Requirements</span></span>  
 <span data-ttu-id="451c7-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="451c7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="451c7-115">**Intestazione:** ClrData.idl</span><span class="sxs-lookup"><span data-stu-id="451c7-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="451c7-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="451c7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="451c7-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="451c7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="451c7-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="451c7-118">See also</span></span>

- [<span data-ttu-id="451c7-119">Funzioni statiche globali di debug</span><span class="sxs-lookup"><span data-stu-id="451c7-119">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
