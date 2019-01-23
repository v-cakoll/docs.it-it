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
ms.openlocfilehash: a46ea398672d44585706be093a080a4bedba7f1e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54535567"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="71dc4-102">Metodo ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="71dc4-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="71dc4-103">Ottiene un valore che indica se il nome fornito corrisponde al nome di un assembly nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="71dc4-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71dc4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="71dc4-104">Syntax</span></span>  
  
```  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="71dc4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="71dc4-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="71dc4-106">[in] Il nome dell'assembly da cercare.</span><span class="sxs-lookup"><span data-stu-id="71dc4-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71dc4-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="71dc4-107">Return Value</span></span>  
  
|<span data-ttu-id="71dc4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71dc4-108">HRESULT</span></span>|<span data-ttu-id="71dc4-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71dc4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71dc4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="71dc4-110">S_OK</span></span>|<span data-ttu-id="71dc4-111">La stringa viene visualizzata nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="71dc4-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="71dc4-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="71dc4-112">S_FALSE</span></span>|<span data-ttu-id="71dc4-113">La stringa non viene visualizzato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="71dc4-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="71dc4-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="71dc4-114">E_FAIL</span></span>|<span data-ttu-id="71dc4-115">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="71dc4-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="71dc4-116">Dopo che un metodo viene restituito E_FAIL, common language runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="71dc4-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="71dc4-117">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="71dc4-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="71dc4-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="71dc4-118">Requirements</span></span>  
 <span data-ttu-id="71dc4-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71dc4-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71dc4-120">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="71dc4-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71dc4-121">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="71dc4-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71dc4-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71dc4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71dc4-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71dc4-123">See also</span></span>
- [<span data-ttu-id="71dc4-124">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="71dc4-124">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="71dc4-125">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="71dc4-125">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="71dc4-126">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="71dc4-126">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="71dc4-127">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="71dc4-127">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
