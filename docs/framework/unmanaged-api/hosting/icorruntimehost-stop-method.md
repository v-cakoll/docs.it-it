---
title: Metodo ICorRuntimeHost::Stop
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Stop
helpviewer_keywords:
- Stop method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Stop method [.NET Framework hosting]
ms.assetid: 46a0d450-b516-4bef-8b71-8d3bf265cbed
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca51b87e7afc8e9e48d541a32b3bd60a19a5ff70
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965960"
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="e2071-102">Metodo ICorRuntimeHost::Stop</span><span class="sxs-lookup"><span data-stu-id="e2071-102">ICorRuntimeHost::Stop Method</span></span>
<span data-ttu-id="e2071-103">Arresta l'esecuzione del codice nel runtime per il processo corrente.</span><span class="sxs-lookup"><span data-stu-id="e2071-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2071-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2071-104">Syntax</span></span>  
  
```cpp  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e2071-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e2071-105">Return Value</span></span>  
  
|<span data-ttu-id="e2071-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e2071-106">HRESULT</span></span>|<span data-ttu-id="e2071-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2071-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e2071-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="e2071-108">S_OK</span></span>|<span data-ttu-id="e2071-109">Operazione completata.</span><span class="sxs-lookup"><span data-stu-id="e2071-109">The operation was successful.</span></span>|  
|<span data-ttu-id="e2071-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e2071-110">S_FALSE</span></span>|<span data-ttu-id="e2071-111">Non è stato possibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="e2071-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="e2071-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e2071-112">E_FAIL</span></span>|<span data-ttu-id="e2071-113">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e2071-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="e2071-114">Se un metodo restituisce E_FAIL, il Common Language Runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="e2071-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="e2071-115">Le chiamate successive a qualsiasi API di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e2071-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e2071-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e2071-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e2071-117">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="e2071-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2071-118">Note</span><span class="sxs-lookup"><span data-stu-id="e2071-118">Remarks</span></span>  
 <span data-ttu-id="e2071-119">In genere non è necessario chiamare il `Stop` metodo, perché l'esecuzione del codice viene arrestata quando il processo viene terminato.</span><span class="sxs-lookup"><span data-stu-id="e2071-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e2071-120">Dopo una chiamata a `Stop`, il CLR non può essere reinizializzato nello stesso processo.</span><span class="sxs-lookup"><span data-stu-id="e2071-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2071-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e2071-121">Requirements</span></span>  
 <span data-ttu-id="e2071-122">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2071-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2071-123">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e2071-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e2071-124">**Libreria** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e2071-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2071-125">**Versioni .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="e2071-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2071-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2071-126">See also</span></span>

- [<span data-ttu-id="e2071-127">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e2071-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
