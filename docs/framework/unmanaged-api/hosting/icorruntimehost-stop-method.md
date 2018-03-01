---
title: Metodo ICorRuntimeHost::Stop
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f9e27bd5d05b10f8db24a1119e4ed3717ce044e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="ecf6a-102">Metodo ICorRuntimeHost::Stop</span><span class="sxs-lookup"><span data-stu-id="ecf6a-102">ICorRuntimeHost::Stop Method</span></span>
<span data-ttu-id="ecf6a-103">Arresta l'esecuzione di codice in fase di esecuzione per il processo corrente.</span><span class="sxs-lookup"><span data-stu-id="ecf6a-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecf6a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ecf6a-104">Syntax</span></span>  
  
```  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ecf6a-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ecf6a-105">Return Value</span></span>  
  
|<span data-ttu-id="ecf6a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ecf6a-106">HRESULT</span></span>|<span data-ttu-id="ecf6a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ecf6a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ecf6a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ecf6a-108">S_OK</span></span>|<span data-ttu-id="ecf6a-109">L'operazione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="ecf6a-109">The operation was successful.</span></span>|  
|<span data-ttu-id="ecf6a-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ecf6a-110">S_FALSE</span></span>|<span data-ttu-id="ecf6a-111">Impossibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="ecf6a-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="ecf6a-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ecf6a-112">E_FAIL</span></span>|<span data-ttu-id="ecf6a-113">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="ecf6a-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="ecf6a-114">Se un metodo restituisce E_FAIL, common language runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="ecf6a-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="ecf6a-115">Le chiamate successive a qualsiasi API di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ecf6a-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ecf6a-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ecf6a-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ecf6a-117">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="ecf6a-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ecf6a-118">Note</span><span class="sxs-lookup"><span data-stu-id="ecf6a-118">Remarks</span></span>  
 <span data-ttu-id="ecf6a-119">In genere non è necessario chiamare il `Stop` metodo, perché il codice interrompe l'esecuzione quando il processo viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="ecf6a-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ecf6a-120">Dopo una chiamata a `Stop`, Common Language Runtime non è possibile reinizializzare nello stesso processo.</span><span class="sxs-lookup"><span data-stu-id="ecf6a-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecf6a-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ecf6a-121">Requirements</span></span>  
 <span data-ttu-id="ecf6a-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecf6a-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecf6a-123">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="ecf6a-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ecf6a-124">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ecf6a-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ecf6a-125">**Versioni di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="ecf6a-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecf6a-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ecf6a-126">See Also</span></span>  
 [<span data-ttu-id="ecf6a-127">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="ecf6a-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
