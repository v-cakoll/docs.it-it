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
ms.openlocfilehash: 62965fa928522052b6885769e02c0211ca8d3fe0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937940"
---
# <a name="ihostassemblymanagergetassemblystore-method"></a><span data-ttu-id="f03ff-102">Metodo IHostAssemblyManager::GetAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="f03ff-102">IHostAssemblyManager::GetAssemblyStore Method</span></span>
<span data-ttu-id="f03ff-103">Ottiene un puntatore a interfaccia a un [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) che rappresenta l'elenco di assembly caricati dall'host.</span><span class="sxs-lookup"><span data-stu-id="f03ff-103">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f03ff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f03ff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f03ff-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f03ff-105">Parameters</span></span>  
 `ppAssemblyStore`  
 <span data-ttu-id="f03ff-106">out Puntatore a funzione a un' `IHostAssemblyStore` istanza o null se l'host non implementa. `IHostAssemblyStore`</span><span class="sxs-lookup"><span data-stu-id="f03ff-106">[out] A function pointer to an `IHostAssemblyStore` instance, or null, if the host does not implement `IHostAssemblyStore`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f03ff-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f03ff-107">Return Value</span></span>  
  
|<span data-ttu-id="f03ff-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f03ff-108">HRESULT</span></span>|<span data-ttu-id="f03ff-109">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="f03ff-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f03ff-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f03ff-110">S_OK</span></span>|<span data-ttu-id="f03ff-111">`GetAssemblyStore`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="f03ff-111">`GetAssemblyStore` returned successfully.</span></span>|  
|<span data-ttu-id="f03ff-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f03ff-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f03ff-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="f03ff-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f03ff-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f03ff-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f03ff-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f03ff-115">The call timed out.</span></span>|  
|<span data-ttu-id="f03ff-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f03ff-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f03ff-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="f03ff-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f03ff-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f03ff-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f03ff-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="f03ff-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f03ff-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f03ff-120">E_FAIL</span></span>|<span data-ttu-id="f03ff-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="f03ff-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f03ff-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="f03ff-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f03ff-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f03ff-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f03ff-124">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="f03ff-124">E_NOINTERFACE</span></span>|<span data-ttu-id="f03ff-125">L'host non fornisce un'implementazione di `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="f03ff-125">The host does not provide an implementation of `IHostAssemblyStore`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f03ff-126">Note</span><span class="sxs-lookup"><span data-stu-id="f03ff-126">Remarks</span></span>  
 <span data-ttu-id="f03ff-127">`IHostAssemblyStore`fornisce metodi che consentono a un host di eseguire l'associazione a assembly e moduli indipendentemente da CLR.</span><span class="sxs-lookup"><span data-stu-id="f03ff-127">`IHostAssemblyStore` provides methods that allow a host to bind to assemblies and modules independently of the CLR.</span></span> <span data-ttu-id="f03ff-128">Gli host forniscono in genere archivi di assembly per consentire il caricamento degli assembly da formati diversi dalla file system.</span><span class="sxs-lookup"><span data-stu-id="f03ff-128">Hosts typically provide assembly stores to allow assemblies to be loaded from formats other than the file system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f03ff-129">Se l'host non implementa `IHostAssemblyStore`, `GetAssemblyStore` deve restituire un valore HRESULT di E_NOINTERFACE e deve essere impostato `ppAssemblyStore` su null.</span><span class="sxs-lookup"><span data-stu-id="f03ff-129">If the host does not implement `IHostAssemblyStore`, `GetAssemblyStore` should return an HRESULT value of E_NOINTERFACE, and should set `ppAssemblyStore` to null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f03ff-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f03ff-130">Requirements</span></span>  
 <span data-ttu-id="f03ff-131">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f03ff-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f03ff-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f03ff-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f03ff-133">**Libreria** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f03ff-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f03ff-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f03ff-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f03ff-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f03ff-135">See also</span></span>

- [<span data-ttu-id="f03ff-136">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="f03ff-136">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="f03ff-137">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="f03ff-137">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
