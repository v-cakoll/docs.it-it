---
title: Metodo ICLRAssemblyReferenceList::IsAssemblyReferenceInList
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList method [.NET Framework hosting]
- IsAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: 8a570813-21be-407e-92a6-7ae8de3bc728
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 557b15fe2bd04a3362532f190a88ee2ad52ed366
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499832"
---
# <a name="iclrassemblyreferencelistisassemblyreferenceinlist-method"></a><span data-ttu-id="01793-102">Metodo ICLRAssemblyReferenceList::IsAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="01793-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList Method</span></span>
<span data-ttu-id="01793-103">Ottiene un valore che indica se il puntatore fornito fa riferimento a un assembly nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="01793-103">Gets a value that indicates whether the supplied pointer refers to an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01793-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01793-104">Syntax</span></span>  
  
```  
HRESULT IsAssemblyReferenceInList (  
    [in] IUnknown *pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01793-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="01793-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="01793-106">[in] Un puntatore a interfaccia per l'assembly da cercare.</span><span class="sxs-lookup"><span data-stu-id="01793-106">[in] An interface pointer to the assembly for which to search.</span></span> <span data-ttu-id="01793-107">I valori validi sono di tipo `IAssemblyName` o `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="01793-107">Valid values are of type `IAssemblyName` or `IReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01793-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="01793-108">Return Value</span></span>  
  
|<span data-ttu-id="01793-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="01793-109">HRESULT</span></span>|<span data-ttu-id="01793-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01793-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="01793-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="01793-111">S_OK</span></span>|<span data-ttu-id="01793-112">La stringa viene visualizzata nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="01793-112">The string appears in the list.</span></span>|  
|<span data-ttu-id="01793-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="01793-113">S_FALSE</span></span>|<span data-ttu-id="01793-114">La stringa non viene visualizzato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="01793-114">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="01793-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01793-115">E_FAIL</span></span>|<span data-ttu-id="01793-116">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="01793-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="01793-117">Dopo che un metodo viene restituito E_FAIL, common language runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="01793-117">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="01793-118">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="01793-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="01793-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="01793-119">Requirements</span></span>  
 <span data-ttu-id="01793-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01793-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01793-121">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="01793-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01793-122">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="01793-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01793-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01793-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01793-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01793-124">See also</span></span>
- [<span data-ttu-id="01793-125">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="01793-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="01793-126">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="01793-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="01793-127">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="01793-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="01793-128">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="01793-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
