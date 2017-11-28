---
title: Metodo ICorRuntimeHost::NextDomain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.NextDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::NextDomain
helpviewer_keywords:
- ICorRuntimeHost::NextDomain method [.NET Framework hosting]
- NextDomain method [.NET Framework hosting]
ms.assetid: fe07a05b-f6d6-44b5-ab01-b9a6eb15c350
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: de7d90ed55cf27aa0b1679b5e55d9f28902b6aeb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorruntimehostnextdomain-method"></a><span data-ttu-id="9b10e-102">Metodo ICorRuntimeHost::NextDomain</span><span class="sxs-lookup"><span data-stu-id="9b10e-102">ICorRuntimeHost::NextDomain Method</span></span>
<span data-ttu-id="9b10e-103">Ottiene un puntatore a interfaccia per il dominio successivo nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="9b10e-103">Gets an interface pointer to the next domain in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b10e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9b10e-104">Syntax</span></span>  
  
```  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b10e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9b10e-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="9b10e-106">[in] Enumeratore che è stato ottenuto tramite una chiamata a [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span><span class="sxs-lookup"><span data-stu-id="9b10e-106">[in] The enumerator that was obtained through a call to [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="9b10e-107">[out] Un puntatore a interfaccia per il <xref:System._AppDomain?displayProperty=nameWithType> tipo che rappresenta il dominio successivo nell'enumerazione oppure null se non esistono altri domini.</span><span class="sxs-lookup"><span data-stu-id="9b10e-107">[out] An interface pointer to the <xref:System._AppDomain?displayProperty=nameWithType> type that represents the next domain in the enumeration, or null, if no more domains exist.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b10e-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9b10e-108">Return Value</span></span>  
  
|<span data-ttu-id="9b10e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9b10e-109">HRESULT</span></span>|<span data-ttu-id="9b10e-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9b10e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9b10e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9b10e-111">S_OK</span></span>|<span data-ttu-id="9b10e-112">L'operazione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="9b10e-112">The operation was successful.</span></span>|  
|<span data-ttu-id="9b10e-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="9b10e-113">S_FALSE</span></span>|<span data-ttu-id="9b10e-114">Impossibile completare l'operazione oppure non sono presenti più domini nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="9b10e-114">The operation failed to complete, or there are no more domains in the enumeration.</span></span>|  
|<span data-ttu-id="9b10e-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9b10e-115">E_FAIL</span></span>|<span data-ttu-id="9b10e-116">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="9b10e-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="9b10e-117">Se un metodo restituisce E_FAIL, common language runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="9b10e-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="9b10e-118">Le chiamate successive a qualsiasi API di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9b10e-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9b10e-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9b10e-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9b10e-120">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9b10e-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9b10e-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9b10e-121">Requirements</span></span>  
 <span data-ttu-id="9b10e-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b10e-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b10e-123">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="9b10e-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9b10e-124">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9b10e-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b10e-125">**Versioni di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="9b10e-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b10e-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b10e-126">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="9b10e-127">ICorRuntimeHost (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="9b10e-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
