---
title: Metodo ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyReferenceList.IsStringAssemblyReferenceInList
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList method [.NET Framework hosting]
- IsStringAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: e6121cc3-2f11-42c7-bdae-47808581ff71
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ff0e51327e0e66c2a282ebf46e6036f81d3d568b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="a0e7c-102">Metodo ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="a0e7c-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="a0e7c-103">Ottiene un valore che indica se il nome fornito corrisponde al nome di un assembly nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a0e7c-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0e7c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a0e7c-104">Syntax</span></span>  
  
```  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0e7c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a0e7c-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="a0e7c-106">[in] Il nome dell'assembly da cercare.</span><span class="sxs-lookup"><span data-stu-id="a0e7c-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0e7c-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a0e7c-107">Return Value</span></span>  
  
|<span data-ttu-id="a0e7c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a0e7c-108">HRESULT</span></span>|<span data-ttu-id="a0e7c-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a0e7c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a0e7c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0e7c-110">S_OK</span></span>|<span data-ttu-id="a0e7c-111">La stringa viene visualizzata nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a0e7c-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="a0e7c-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a0e7c-112">S_FALSE</span></span>|<span data-ttu-id="a0e7c-113">La stringa non viene visualizzato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a0e7c-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="a0e7c-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a0e7c-114">E_FAIL</span></span>|<span data-ttu-id="a0e7c-115">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="a0e7c-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a0e7c-116">Se un metodo restituisce E_FAIL, common language runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="a0e7c-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="a0e7c-117">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a0e7c-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a0e7c-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a0e7c-118">Requirements</span></span>  
 <span data-ttu-id="a0e7c-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0e7c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0e7c-120">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="a0e7c-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0e7c-121">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a0e7c-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0e7c-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0e7c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0e7c-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0e7c-123">See Also</span></span>  
 [<span data-ttu-id="a0e7c-124">ICLRAssemblyIdentityManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a0e7c-124">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="a0e7c-125">ICLRAssemblyReferenceList (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a0e7c-125">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="a0e7c-126">IHostAssemblyManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a0e7c-126">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="a0e7c-127">IHostAssemblyStore (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a0e7c-127">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
