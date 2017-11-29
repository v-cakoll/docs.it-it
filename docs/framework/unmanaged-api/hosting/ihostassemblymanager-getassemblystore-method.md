---
title: Metodo IHostAssemblyManager::GetAssemblyStore
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyManager.GetAssemblyStore
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyManager::GetAssemblyStore
helpviewer_keywords:
- IHostAssemblyManager::GetAssemblyStore method [.NET Framework hosting]
- GetAssemblyStore method [.NET Framework hosting]
ms.assetid: d0f74593-9bb1-4a11-8096-e29734b20698
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d838ee8383a4e11f5d43c4a3751c4a90503906fb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostassemblymanagergetassemblystore-method"></a><span data-ttu-id="f1684-102">Metodo IHostAssemblyManager::GetAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="f1684-102">IHostAssemblyManager::GetAssemblyStore Method</span></span>
<span data-ttu-id="f1684-103">Ottiene un puntatore a interfaccia a un [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) che rappresenta l'elenco degli assembly caricati dall'host.</span><span class="sxs-lookup"><span data-stu-id="f1684-103">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1684-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1684-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f1684-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f1684-105">Parameters</span></span>  
 `ppAssemblyStore`  
 <span data-ttu-id="f1684-106">[out] Puntatore a funzione a un `IHostAssemblyStore` istanza oppure null se l'host non implementa `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="f1684-106">[out] A function pointer to an `IHostAssemblyStore` instance, or null, if the host does not implement `IHostAssemblyStore`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1684-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f1684-107">Return Value</span></span>  
  
|<span data-ttu-id="f1684-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f1684-108">HRESULT</span></span>|<span data-ttu-id="f1684-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1684-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f1684-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f1684-110">S_OK</span></span>|<span data-ttu-id="f1684-111">`GetAssemblyStore`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="f1684-111">`GetAssemblyStore` returned successfully.</span></span>|  
|<span data-ttu-id="f1684-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f1684-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f1684-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f1684-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f1684-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f1684-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f1684-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f1684-115">The call timed out.</span></span>|  
|<span data-ttu-id="f1684-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f1684-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f1684-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="f1684-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f1684-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f1684-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f1684-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="f1684-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f1684-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f1684-120">E_FAIL</span></span>|<span data-ttu-id="f1684-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="f1684-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f1684-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="f1684-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f1684-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f1684-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f1684-124">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="f1684-124">E_NOINTERFACE</span></span>|<span data-ttu-id="f1684-125">L'host non fornisce un'implementazione di `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="f1684-125">The host does not provide an implementation of `IHostAssemblyStore`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1684-126">Note</span><span class="sxs-lookup"><span data-stu-id="f1684-126">Remarks</span></span>  
 <span data-ttu-id="f1684-127">`IHostAssemblyStore`fornisce metodi che consentono a un host per l'associazione di assembly e moduli in modo indipendente da CLR.</span><span class="sxs-lookup"><span data-stu-id="f1684-127">`IHostAssemblyStore` provides methods that allow a host to bind to assemblies and modules independently of the CLR.</span></span> <span data-ttu-id="f1684-128">Gli host in genere forniscono archivi di assembly per consentire agli assembly devono essere caricati da formati diversi da file system.</span><span class="sxs-lookup"><span data-stu-id="f1684-128">Hosts typically provide assembly stores to allow assemblies to be loaded from formats other than the file system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1684-129">Se l'host non implementa `IHostAssemblyStore`, `GetAssemblyStore` deve restituire un valore HRESULT di tipo E_NOINTERFACE e deve impostare `ppAssemblyStore` su null.</span><span class="sxs-lookup"><span data-stu-id="f1684-129">If the host does not implement `IHostAssemblyStore`, `GetAssemblyStore` should return an HRESULT value of E_NOINTERFACE, and should set `ppAssemblyStore` to null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1684-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f1684-130">Requirements</span></span>  
 <span data-ttu-id="f1684-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1684-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1684-132">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="f1684-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f1684-133">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f1684-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f1684-134">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1684-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1684-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1684-135">See Also</span></span>  
 [<span data-ttu-id="f1684-136">IHostAssemblyManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="f1684-136">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="f1684-137">IHostAssemblyStore (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="f1684-137">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
