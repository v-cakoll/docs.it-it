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
ms.openlocfilehash: 7f09cb2264b21fdfbc892069f2c2f0a963b131f8
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615969"
---
# <a name="iclrassemblyidentitymanagergetclrassemblyreferencelist-method"></a><span data-ttu-id="a817e-102">Metodo ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="a817e-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList Method</span></span>
<span data-ttu-id="a817e-103">Ottiene un puntatore a interfaccia a un'istanza di [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) dall'elenco fornito di identità di assembly parziali.</span><span class="sxs-lookup"><span data-stu-id="a817e-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a817e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a817e-104">Syntax</span></span>  
  
```cpp  
HRESULT  GetCLRAssemblyReferenceList (  
    [in] LPCWSTR *ppwzAssemblyReferences,  
    [in] DWORD    dwNumOfReferences,  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a817e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a817e-105">Parameters</span></span>  
 `ppwzAssemblyReferences`  
 <span data-ttu-id="a817e-106">in Una matrice di stringhe con terminazione null nel formato "nome, proprietà = valore..." che specificano un elenco di identità di assembly parziali.</span><span class="sxs-lookup"><span data-stu-id="a817e-106">[in] An array of null-terminated strings in the form "name, property=value..." that specify a list of partial assembly identities.</span></span>  
  
 `dwNumOfReferences`  
 <span data-ttu-id="a817e-107">in Numero di elementi in `ppwzAssemblyReferences` .</span><span class="sxs-lookup"><span data-stu-id="a817e-107">[in] The number of items in `ppwzAssemblyReferences`.</span></span>  
  
 `ppReferenceList`  
 <span data-ttu-id="a817e-108">out Puntatore di interfaccia a un `ICLRAssemblyReferenceList` oggetto che contiene i dati di identità dell'assembly per l'elenco di assembly specificato in `ppwzAssemblyReferences` .</span><span class="sxs-lookup"><span data-stu-id="a817e-108">[out] An interface pointer to an `ICLRAssemblyReferenceList` object that contains the assembly identity data for the list of assemblies specified in `ppwzAssemblyReferences`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a817e-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a817e-109">Return Value</span></span>  
  
|<span data-ttu-id="a817e-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a817e-110">HRESULT</span></span>|<span data-ttu-id="a817e-111">Description</span><span class="sxs-lookup"><span data-stu-id="a817e-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a817e-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a817e-112">S_OK</span></span>|<span data-ttu-id="a817e-113">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="a817e-113">The method returned successfully.</span></span>|  
|<span data-ttu-id="a817e-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a817e-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a817e-115">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="a817e-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a817e-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a817e-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a817e-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="a817e-117">The call timed out.</span></span>|  
|<span data-ttu-id="a817e-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a817e-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a817e-119">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="a817e-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a817e-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a817e-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a817e-121">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="a817e-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a817e-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a817e-122">E_FAIL</span></span>|<span data-ttu-id="a817e-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="a817e-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a817e-124">Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="a817e-124">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a817e-125">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a817e-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a817e-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a817e-126">Requirements</span></span>  
 <span data-ttu-id="a817e-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a817e-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a817e-128">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a817e-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a817e-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a817e-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a817e-130">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a817e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a817e-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a817e-131">See also</span></span>

- [<span data-ttu-id="a817e-132">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="a817e-132">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="a817e-133">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="a817e-133">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
