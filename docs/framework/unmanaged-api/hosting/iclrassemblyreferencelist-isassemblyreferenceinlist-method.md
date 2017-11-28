---
title: Metodo ICLRAssemblyReferenceList::IsAssemblyReferenceInList
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyReferenceList.IsAssemblyReferenceInList
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyReferenceList::IsAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList method [.NET Framework hosting]
- IsAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: 8a570813-21be-407e-92a6-7ae8de3bc728
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 923f7f4178d3c310b51ebb7e7df06040ba69f9c7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrassemblyreferencelistisassemblyreferenceinlist-method"></a><span data-ttu-id="df4d8-102">Metodo ICLRAssemblyReferenceList::IsAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="df4d8-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList Method</span></span>
<span data-ttu-id="df4d8-103">Ottiene un valore che indica se il puntatore fornito fa riferimento a un assembly nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="df4d8-103">Gets a value that indicates whether the supplied pointer refers to an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df4d8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="df4d8-104">Syntax</span></span>  
  
```  
HRESULT IsAssemblyReferenceInList (  
    [in] IUnknown *pName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df4d8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="df4d8-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="df4d8-106">[in] Un puntatore a interfaccia per l'assembly da cercare.</span><span class="sxs-lookup"><span data-stu-id="df4d8-106">[in] An interface pointer to the assembly for which to search.</span></span> <span data-ttu-id="df4d8-107">I valori validi sono di tipo `IAssemblyName` o `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="df4d8-107">Valid values are of type `IAssemblyName` or `IReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df4d8-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="df4d8-108">Return Value</span></span>  
  
|<span data-ttu-id="df4d8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="df4d8-109">HRESULT</span></span>|<span data-ttu-id="df4d8-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="df4d8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="df4d8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="df4d8-111">S_OK</span></span>|<span data-ttu-id="df4d8-112">La stringa viene visualizzata nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="df4d8-112">The string appears in the list.</span></span>|  
|<span data-ttu-id="df4d8-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="df4d8-113">S_FALSE</span></span>|<span data-ttu-id="df4d8-114">La stringa non viene visualizzato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="df4d8-114">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="df4d8-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="df4d8-115">E_FAIL</span></span>|<span data-ttu-id="df4d8-116">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="df4d8-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="df4d8-117">Se un metodo restituisce E_FAIL, common language runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="df4d8-117">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="df4d8-118">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="df4d8-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="df4d8-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="df4d8-119">Requirements</span></span>  
 <span data-ttu-id="df4d8-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df4d8-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df4d8-121">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="df4d8-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="df4d8-122">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="df4d8-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df4d8-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df4d8-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df4d8-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df4d8-124">See Also</span></span>  
 [<span data-ttu-id="df4d8-125">ICLRAssemblyIdentityManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="df4d8-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="df4d8-126">ICLRAssemblyReferenceList (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="df4d8-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="df4d8-127">IHostAssemblyManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="df4d8-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="df4d8-128">IHostAssemblyStore (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="df4d8-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
