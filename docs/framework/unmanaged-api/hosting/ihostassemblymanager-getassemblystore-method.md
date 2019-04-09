---
title: Metodo IHostAssemblyManager::GetAssemblyStore
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetAssemblyStore
helpviewer_keywords:
- IHostAssemblyManager::GetAssemblyStore method [.NET Framework hosting]
- GetAssemblyStore method [.NET Framework hosting]
ms.assetid: d0f74593-9bb1-4a11-8096-e29734b20698
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 35e38949ce945d93216daffd3c0d91dad6c8739b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092773"
---
# <a name="ihostassemblymanagergetassemblystore-method"></a><span data-ttu-id="c602d-102">Metodo IHostAssemblyManager::GetAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="c602d-102">IHostAssemblyManager::GetAssemblyStore Method</span></span>
<span data-ttu-id="c602d-103">Ottiene un puntatore a interfaccia a un [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) che rappresenta l'elenco di assembly caricati dall'host.</span><span class="sxs-lookup"><span data-stu-id="c602d-103">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c602d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c602d-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c602d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c602d-105">Parameters</span></span>  
 `ppAssemblyStore`  
 <span data-ttu-id="c602d-106">[out] Un puntatore a funzione a un `IHostAssemblyStore` dell'istanza o null se l'host non implementa `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="c602d-106">[out] A function pointer to an `IHostAssemblyStore` instance, or null, if the host does not implement `IHostAssemblyStore`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c602d-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c602d-107">Return Value</span></span>  
  
|<span data-ttu-id="c602d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c602d-108">HRESULT</span></span>|<span data-ttu-id="c602d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c602d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c602d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c602d-110">S_OK</span></span>|`GetAssemblyStore` <span data-ttu-id="c602d-111">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="c602d-111">returned successfully.</span></span>|  
|<span data-ttu-id="c602d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c602d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c602d-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c602d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c602d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c602d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c602d-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c602d-115">The call timed out.</span></span>|  
|<span data-ttu-id="c602d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c602d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c602d-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="c602d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c602d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c602d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c602d-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="c602d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c602d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c602d-120">E_FAIL</span></span>|<span data-ttu-id="c602d-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c602d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c602d-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="c602d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c602d-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c602d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c602d-124">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="c602d-124">E_NOINTERFACE</span></span>|<span data-ttu-id="c602d-125">L'host non fornisce un'implementazione di `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="c602d-125">The host does not provide an implementation of `IHostAssemblyStore`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c602d-126">Note</span><span class="sxs-lookup"><span data-stu-id="c602d-126">Remarks</span></span>  
 `IHostAssemblyStore` <span data-ttu-id="c602d-127">fornisce metodi che consentono a un host da associare agli assembly e moduli indipendentemente da CLR.</span><span class="sxs-lookup"><span data-stu-id="c602d-127">provides methods that allow a host to bind to assemblies and modules independently of the CLR.</span></span> <span data-ttu-id="c602d-128">Gli host forniscono in genere gli archivi di assembly per consentire il caricamento da formati diversi da file system di assembly.</span><span class="sxs-lookup"><span data-stu-id="c602d-128">Hosts typically provide assembly stores to allow assemblies to be loaded from formats other than the file system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c602d-129">Se l'host non implementa `IHostAssemblyStore`, `GetAssemblyStore` deve restituire un valore HRESULT di tipo E_NOINTERFACE e devono impostare `ppAssemblyStore` su null.</span><span class="sxs-lookup"><span data-stu-id="c602d-129">If the host does not implement `IHostAssemblyStore`, `GetAssemblyStore` should return an HRESULT value of E_NOINTERFACE, and should set `ppAssemblyStore` to null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c602d-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c602d-130">Requirements</span></span>  
 <span data-ttu-id="c602d-131">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c602d-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c602d-132">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c602d-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c602d-133">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c602d-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c602d-134">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c602d-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c602d-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c602d-135">See also</span></span>

- [<span data-ttu-id="c602d-136">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="c602d-136">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="c602d-137">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="c602d-137">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
