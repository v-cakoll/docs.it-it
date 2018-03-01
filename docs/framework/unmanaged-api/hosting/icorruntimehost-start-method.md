---
title: Metodo ICorRuntimeHost::Start
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
- ICorRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Start
helpviewer_keywords:
- Start method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Start method [.NET Framework hosting]
ms.assetid: c66f3ac5-6489-484a-9bed-c31b711cee01
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2d79046db904de68e5b24b2f96206bb1de2de470
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehoststart-method"></a><span data-ttu-id="67265-102">Metodo ICorRuntimeHost::Start</span><span class="sxs-lookup"><span data-stu-id="67265-102">ICorRuntimeHost::Start Method</span></span>
<span data-ttu-id="67265-103">Avvio di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="67265-103">Starts the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67265-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="67265-104">Syntax</span></span>  
  
```  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="67265-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="67265-105">Return Value</span></span>  
  
|<span data-ttu-id="67265-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="67265-106">HRESULT</span></span>|<span data-ttu-id="67265-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="67265-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="67265-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="67265-108">S_OK</span></span>|<span data-ttu-id="67265-109">L'operazione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="67265-109">The operation was successful.</span></span>|  
|<span data-ttu-id="67265-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="67265-110">S_FALSE</span></span>|<span data-ttu-id="67265-111">Impossibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="67265-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="67265-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="67265-112">E_FAIL</span></span>|<span data-ttu-id="67265-113">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="67265-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="67265-114">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="67265-114">If a method returns E_FAIL, the CLR is no longer usable in the process.</span></span> <span data-ttu-id="67265-115">Le chiamate successive a qualsiasi API di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="67265-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="67265-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="67265-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="67265-117">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="67265-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67265-118">Note</span><span class="sxs-lookup"><span data-stu-id="67265-118">Remarks</span></span>  
 <span data-ttu-id="67265-119">Non è in genere necessario chiamare il `Start` metodo, perché Common Language Runtime viene avviato automaticamente alla prima richiesta per eseguire il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="67265-119">It is typically not necessary to call the `Start` method, because the CLR starts automatically upon the first request to run managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67265-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="67265-120">Requirements</span></span>  
 <span data-ttu-id="67265-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67265-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67265-122">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="67265-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="67265-123">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="67265-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67265-124">**Versioni di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="67265-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67265-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67265-125">See Also</span></span>  
 [<span data-ttu-id="67265-126">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="67265-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
