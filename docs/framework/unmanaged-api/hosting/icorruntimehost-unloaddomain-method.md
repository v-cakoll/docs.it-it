---
title: Metodo ICorRuntimeHost::UnloadDomain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.UnloadDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::UnloadDomain
helpviewer_keywords:
- ICorRuntimeHost::UnloadDomain method [.NET Framework hosting]
- UnloadDomain method [.NET Framework hosting]
ms.assetid: dd9e9204-a80d-44f3-8192-779224b35056
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 054615e08da785f34be59c52488b8a4dcc2d7d98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="1a98c-102">Metodo ICorRuntimeHost::UnloadDomain</span><span class="sxs-lookup"><span data-stu-id="1a98c-102">ICorRuntimeHost::UnloadDomain Method</span></span>
<span data-ttu-id="1a98c-103">Scarica il dominio di applicazione specificata dal processo corrente.</span><span class="sxs-lookup"><span data-stu-id="1a98c-103">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a98c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1a98c-104">Syntax</span></span>  
  
```  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1a98c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1a98c-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="1a98c-106">[in] Un puntatore di tipo <xref:System._AppDomain?displayProperty=nameWithType> che rappresenta il dominio per essere scaricato.</span><span class="sxs-lookup"><span data-stu-id="1a98c-106">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a98c-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1a98c-107">Return Value</span></span>  
  
|<span data-ttu-id="1a98c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1a98c-108">HRESULT</span></span>|<span data-ttu-id="1a98c-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1a98c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1a98c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1a98c-110">S_OK</span></span>|<span data-ttu-id="1a98c-111">L'operazione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="1a98c-111">The operation was successful.</span></span>|  
|<span data-ttu-id="1a98c-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="1a98c-112">S_FALSE</span></span>|<span data-ttu-id="1a98c-113">Impossibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="1a98c-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="1a98c-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1a98c-114">E_FAIL</span></span>|<span data-ttu-id="1a98c-115">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="1a98c-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="1a98c-116">Se un metodo restituisce E_FAIL, common language runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="1a98c-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="1a98c-117">Le chiamate successive a qualsiasi API di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1a98c-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1a98c-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1a98c-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1a98c-119">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="1a98c-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1a98c-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1a98c-120">Requirements</span></span>  
 <span data-ttu-id="1a98c-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a98c-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a98c-122">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="1a98c-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1a98c-123">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1a98c-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1a98c-124">**Versione di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="1a98c-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a98c-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a98c-125">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="1a98c-126">ICorRuntimeHost (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="1a98c-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
