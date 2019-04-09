---
title: Metodo ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsStringAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList method [.NET Framework hosting]
- IsStringAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: e6121cc3-2f11-42c7-bdae-47808581ff71
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de17a91b5093372579a4d9435532a95406addd0a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216899"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="120ac-102">Metodo ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="120ac-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="120ac-103">Ottiene un valore che indica se il nome fornito corrisponde al nome di un assembly nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="120ac-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="120ac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="120ac-104">Syntax</span></span>  
  
```  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="120ac-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="120ac-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="120ac-106">[in] Il nome dell'assembly da cercare.</span><span class="sxs-lookup"><span data-stu-id="120ac-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="120ac-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="120ac-107">Return Value</span></span>  
  
|<span data-ttu-id="120ac-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="120ac-108">HRESULT</span></span>|<span data-ttu-id="120ac-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="120ac-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="120ac-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="120ac-110">S_OK</span></span>|<span data-ttu-id="120ac-111">La stringa viene visualizzata nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="120ac-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="120ac-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="120ac-112">S_FALSE</span></span>|<span data-ttu-id="120ac-113">La stringa non viene visualizzato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="120ac-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="120ac-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="120ac-114">E_FAIL</span></span>|<span data-ttu-id="120ac-115">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="120ac-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="120ac-116">Dopo che un metodo viene restituito E_FAIL, common language runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="120ac-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="120ac-117">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="120ac-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="120ac-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="120ac-118">Requirements</span></span>  
 <span data-ttu-id="120ac-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="120ac-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="120ac-120">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="120ac-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="120ac-121">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="120ac-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="120ac-122">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="120ac-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="120ac-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="120ac-123">See also</span></span>

- [<span data-ttu-id="120ac-124">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="120ac-124">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="120ac-125">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="120ac-125">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="120ac-126">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="120ac-126">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="120ac-127">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="120ac-127">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
