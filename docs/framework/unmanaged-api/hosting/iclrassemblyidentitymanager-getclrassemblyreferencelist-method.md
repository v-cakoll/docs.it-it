---
title: Metodo ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetCLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList
helpviewer_keywords:
- GetClrAssemblyReferenceList method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList method [.NET Framework hosting]
ms.assetid: cb5ffae5-287b-4a87-9ca8-7ce3ae0601b7
topic_type:
- apiref
ms.openlocfilehash: 54c11e78438ae97e1fc0c715c9161361784b3be6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126725"
---
# <a name="iclrassemblyidentitymanagergetclrassemblyreferencelist-method"></a><span data-ttu-id="f11c6-102">Metodo ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="f11c6-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList Method</span></span>
<span data-ttu-id="f11c6-103">Ottiene un puntatore a interfaccia a un'istanza di [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) dall'elenco fornito di identità di assembly parziali.</span><span class="sxs-lookup"><span data-stu-id="f11c6-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f11c6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f11c6-104">Syntax</span></span>  
  
```cpp  
HRESULT  GetCLRAssemblyReferenceList (  
    [in] LPCWSTR *ppwzAssemblyReferences,  
    [in] DWORD    dwNumOfReferences,  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f11c6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f11c6-105">Parameters</span></span>  
 `ppwzAssemblyReferences`  
 <span data-ttu-id="f11c6-106">in Una matrice di stringhe con terminazione null nel formato "nome, proprietà = valore..." che specificano un elenco di identità di assembly parziali.</span><span class="sxs-lookup"><span data-stu-id="f11c6-106">[in] An array of null-terminated strings in the form "name, property=value..." that specify a list of partial assembly identities.</span></span>  
  
 `dwNumOfReferences`  
 <span data-ttu-id="f11c6-107">in Numero di elementi in `ppwzAssemblyReferences`.</span><span class="sxs-lookup"><span data-stu-id="f11c6-107">[in] The number of items in `ppwzAssemblyReferences`.</span></span>  
  
 `ppReferenceList`  
 <span data-ttu-id="f11c6-108">out Puntatore a un'interfaccia a un oggetto `ICLRAssemblyReferenceList` contenente i dati di identità dell'assembly per l'elenco di assembly specificato in `ppwzAssemblyReferences`.</span><span class="sxs-lookup"><span data-stu-id="f11c6-108">[out] An interface pointer to an `ICLRAssemblyReferenceList` object that contains the assembly identity data for the list of assemblies specified in `ppwzAssemblyReferences`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f11c6-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f11c6-109">Return Value</span></span>  
  
|<span data-ttu-id="f11c6-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f11c6-110">HRESULT</span></span>|<span data-ttu-id="f11c6-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f11c6-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f11c6-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f11c6-112">S_OK</span></span>|<span data-ttu-id="f11c6-113">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="f11c6-113">The method returned successfully.</span></span>|  
|<span data-ttu-id="f11c6-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f11c6-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f11c6-115">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="f11c6-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f11c6-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f11c6-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f11c6-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f11c6-117">The call timed out.</span></span>|  
|<span data-ttu-id="f11c6-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f11c6-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f11c6-119">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="f11c6-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f11c6-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f11c6-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f11c6-121">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="f11c6-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f11c6-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f11c6-122">E_FAIL</span></span>|<span data-ttu-id="f11c6-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="f11c6-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f11c6-124">Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="f11c6-124">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f11c6-125">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f11c6-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f11c6-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f11c6-126">Requirements</span></span>  
 <span data-ttu-id="f11c6-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f11c6-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f11c6-128">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f11c6-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f11c6-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f11c6-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f11c6-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f11c6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f11c6-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f11c6-131">See also</span></span>

- [<span data-ttu-id="f11c6-132">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="f11c6-132">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="f11c6-133">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="f11c6-133">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
