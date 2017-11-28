---
title: Metodo ICorRuntimeHost::GetDefaultDomain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.GetDefaultDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::GetDefaultDomain
helpviewer_keywords:
- ICorRuntimeHost::GetDefaultDomain method [.NET Framework hosting]
- GetDefaultDomain method [.NET Framework hosting]
ms.assetid: 5e17a6fc-f335-4aae-9bb0-c3e1271a9426
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4c482247a0a227c202bb81db09d13ad9af71e60f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorruntimehostgetdefaultdomain-method"></a><span data-ttu-id="4a2b2-102">Metodo ICorRuntimeHost::GetDefaultDomain</span><span class="sxs-lookup"><span data-stu-id="4a2b2-102">ICorRuntimeHost::GetDefaultDomain Method</span></span>
<span data-ttu-id="4a2b2-103">Ottiene un puntatore a interfaccia di tipo <xref:System._AppDomain?displayProperty=nameWithType> che rappresenta il dominio predefinito per il processo corrente.</span><span class="sxs-lookup"><span data-stu-id="4a2b2-103">Gets an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the default domain for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a2b2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a2b2-104">Syntax</span></span>  
  
```  
HRESULT GetDefaultDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4a2b2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4a2b2-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="4a2b2-106">[out] Un puntatore a interfaccia di tipo <xref:System._AppDomain?displayProperty=nameWithType> per il <xref:System.AppDomain> istanza che rappresenta il dominio applicazione predefinito per il processo.</span><span class="sxs-lookup"><span data-stu-id="4a2b2-106">[out] An interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> to the <xref:System.AppDomain> instance that represents the default application domain for the process.</span></span>  
  
 <span data-ttu-id="4a2b2-107">Il puntatore è tipizzato `IUnknown`, i chiamanti devono in genere utilizzare `QueryInterface` per ottenere un puntatore a interfaccia di tipo <xref:System._AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4a2b2-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a2b2-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4a2b2-108">Return Value</span></span>  
  
|<span data-ttu-id="4a2b2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4a2b2-109">HRESULT</span></span>|<span data-ttu-id="4a2b2-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a2b2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4a2b2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4a2b2-111">S_OK</span></span>|<span data-ttu-id="4a2b2-112">L'operazione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="4a2b2-112">The operation was successful.</span></span>|  
|<span data-ttu-id="4a2b2-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="4a2b2-113">S_FALSE</span></span>|<span data-ttu-id="4a2b2-114">Impossibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="4a2b2-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="4a2b2-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4a2b2-115">E_FAIL</span></span>|<span data-ttu-id="4a2b2-116">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="4a2b2-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="4a2b2-117">Se un metodo restituisce E_FAIL, common language runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="4a2b2-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="4a2b2-118">Le chiamate successive a qualsiasi API di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4a2b2-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4a2b2-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4a2b2-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4a2b2-120">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4a2b2-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4a2b2-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4a2b2-121">Requirements</span></span>  
 <span data-ttu-id="4a2b2-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a2b2-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a2b2-123">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="4a2b2-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4a2b2-124">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4a2b2-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a2b2-125">**Versioni di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="4a2b2-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a2b2-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a2b2-126">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="4a2b2-127">ICorRuntimeHost (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4a2b2-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
