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
ms.openlocfilehash: 34aae3cd913465bc3167d6c5eee9873d212fa4ac
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420689"
---
# <a name="pfn_clrdatacreateinstance-function-pointer"></a><span data-ttu-id="1152c-102">Puntatore alla funzione PFN_CLRDataCreateInstance</span><span class="sxs-lookup"><span data-stu-id="1152c-102">PFN_CLRDataCreateInstance Function Pointer</span></span>
<span data-ttu-id="1152c-103">Punta a una funzione che crea un oggetto interfaccia per l'elemento di destinazione specificato.</span><span class="sxs-lookup"><span data-stu-id="1152c-103">Points to a function that creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1152c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1152c-104">Syntax</span></span>  
  
```cpp  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1152c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1152c-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="1152c-106">in Identificatore dell'interfaccia di cui creare un'istanza.</span><span class="sxs-lookup"><span data-stu-id="1152c-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="1152c-107">in Puntatore a un oggetto [ICLRDataTarget](iclrdatatarget-interface.md) implementato dall'utente che rappresenta l'elemento di destinazione per il quale creare l'oggetto interfaccia.</span><span class="sxs-lookup"><span data-stu-id="1152c-107">[in] A pointer to a user-implemented [ICLRDataTarget](iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="1152c-108">out Puntatore all'indirizzo dell'oggetto interfaccia restituito.</span><span class="sxs-lookup"><span data-stu-id="1152c-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1152c-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1152c-109">Remarks</span></span>  
 <span data-ttu-id="1152c-110">L' `ICLRDataTarget` oggetto viene implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="1152c-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="1152c-111">L'implementazione dipende dal tipo di elemento di destinazione rappresentato.</span><span class="sxs-lookup"><span data-stu-id="1152c-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="1152c-112">L'elemento di destinazione può essere un processo, un dump della memoria, un computer remoto e così via.</span><span class="sxs-lookup"><span data-stu-id="1152c-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1152c-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1152c-113">Requirements</span></span>  
 <span data-ttu-id="1152c-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1152c-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1152c-115">**Intestazione:** ClrData. idl</span><span class="sxs-lookup"><span data-stu-id="1152c-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="1152c-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1152c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1152c-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1152c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1152c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1152c-118">See also</span></span>

- [<span data-ttu-id="1152c-119">Funzioni statiche globali di debug</span><span class="sxs-lookup"><span data-stu-id="1152c-119">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
