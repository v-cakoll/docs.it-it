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
ms.openlocfilehash: 587861529c340fad9fd817b904e4d3651b236e8d
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805076"
---
# <a name="ihostassemblymanagergetassemblystore-method"></a><span data-ttu-id="c6c1d-102">Metodo IHostAssemblyManager::GetAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="c6c1d-102">IHostAssemblyManager::GetAssemblyStore Method</span></span>
<span data-ttu-id="c6c1d-103">Ottiene un puntatore a interfaccia a un [IHostAssemblyStore](ihostassemblystore-interface.md) che rappresenta l'elenco di assembly caricati dall'host.</span><span class="sxs-lookup"><span data-stu-id="c6c1d-103">Gets an interface pointer to an [IHostAssemblyStore](ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6c1d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c6c1d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6c1d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c6c1d-105">Parameters</span></span>  
 `ppAssemblyStore`  
 <span data-ttu-id="c6c1d-106">out Puntatore a funzione a un' `IHostAssemblyStore` istanza o null se l'host non implementa `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="c6c1d-106">[out] A function pointer to an `IHostAssemblyStore` instance, or null, if the host does not implement `IHostAssemblyStore`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6c1d-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c6c1d-107">Return Value</span></span>  
  
|<span data-ttu-id="c6c1d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c6c1d-108">HRESULT</span></span>|<span data-ttu-id="c6c1d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c6c1d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c6c1d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c6c1d-110">S_OK</span></span>|<span data-ttu-id="c6c1d-111">`GetAssemblyStore`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="c6c1d-111">`GetAssemblyStore` returned successfully.</span></span>|  
|<span data-ttu-id="c6c1d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c6c1d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c6c1d-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="c6c1d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c6c1d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c6c1d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c6c1d-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c6c1d-115">The call timed out.</span></span>|  
|<span data-ttu-id="c6c1d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c6c1d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c6c1d-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="c6c1d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c6c1d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c6c1d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c6c1d-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="c6c1d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c6c1d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c6c1d-120">E_FAIL</span></span>|<span data-ttu-id="c6c1d-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c6c1d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c6c1d-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="c6c1d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c6c1d-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c6c1d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c6c1d-124">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="c6c1d-124">E_NOINTERFACE</span></span>|<span data-ttu-id="c6c1d-125">L'host non fornisce un'implementazione di `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="c6c1d-125">The host does not provide an implementation of `IHostAssemblyStore`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6c1d-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c6c1d-126">Remarks</span></span>  
 <span data-ttu-id="c6c1d-127">`IHostAssemblyStore`fornisce metodi che consentono a un host di eseguire l'associazione a assembly e moduli indipendentemente da CLR.</span><span class="sxs-lookup"><span data-stu-id="c6c1d-127">`IHostAssemblyStore` provides methods that allow a host to bind to assemblies and modules independently of the CLR.</span></span> <span data-ttu-id="c6c1d-128">Gli host forniscono in genere archivi di assembly per consentire il caricamento degli assembly da formati diversi dalla file system.</span><span class="sxs-lookup"><span data-stu-id="c6c1d-128">Hosts typically provide assembly stores to allow assemblies to be loaded from formats other than the file system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c6c1d-129">Se l'host non implementa `IHostAssemblyStore` , `GetAssemblyStore` deve restituire un valore HRESULT di E_NOINTERFACE e deve `ppAssemblyStore` essere impostato su null.</span><span class="sxs-lookup"><span data-stu-id="c6c1d-129">If the host does not implement `IHostAssemblyStore`, `GetAssemblyStore` should return an HRESULT value of E_NOINTERFACE, and should set `ppAssemblyStore` to null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6c1d-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c6c1d-130">Requirements</span></span>  
 <span data-ttu-id="c6c1d-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6c1d-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6c1d-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c6c1d-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6c1d-133">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c6c1d-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6c1d-134">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6c1d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6c1d-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6c1d-135">See also</span></span>

- [<span data-ttu-id="c6c1d-136">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="c6c1d-136">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="c6c1d-137">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="c6c1d-137">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
